---
title: "🎅 LINQing Up Christmas: .NET 9 Features in Action"
tags: dotnet-9 CsAdvent LINQ
---

In November 2024, Microsoft released .NET 9 and C# 13. There are all sorts of gifts for .NET developers in this release. Today, I want to share one of my favorite ones – the LINQ updates! What better way to share news at this time of year but with a holiday theme – and especially as this post is a part of C# Advent!

## Index: Ranking Santa’s Reindeer for the Big Night 🦌

The first method I want to point out is `Index`. It is a new method for `IEnumerable` collections and returns a tuple of `(int index, TSource item)`. Consider this block of code, which will output each reindeer and their position:

```csharp
var reindeerNames = new[] 
{ 
    "Dasher", "Dancer", "Prancer", "Vixen", "Comet", "Cupid", "Donner", "Blitzen", "Rudolph" 
};

var reindeerIndex = reindeerNames.Index();

foreach (var (index, name) in reindeerIndex)
{
    Console.WriteLine($"{name} is at position {index + 1}");
}
```

The output will look something like this:

```text
Dasher is at position 1
Dancer is at position 2
...
Rudolph is at position 9
```

When you need to show positions of items within an IEnumerable, then Index is your go-to!

## CountBy: Tallying Santa’s Toy Inventory 🎁?

The next method I want to mention is `CountBy`. This allows you to easily aggregate by a group and get the counts for that group.

Consider this code that will get us the count for each of these presents:

```csharp
var gifts = new[]
{
    "Doll", "Train", "Doll", "Bicycle", "Train", "Doll", "Bicycle", "Puzzle"
};

var giftCounts = gifts.CountBy(gift => gift);

foreach (var (gift, count) in giftCounts)
{
    Console.WriteLine($"{gift}: {count}");
}
```

How many dolls, trains, bicycles, and puzzles does he have?

```text
Doll: 3
Train: 2
Bicycle: 2
Puzzle: 1
```

Use `CountBy` when it comes to counting in groups.

## AggregateBy: Weighing the Sleigh for Christmas Eve 🛷

The last method I want to mention for LINQ in .NET 9 is `AggregateBy`. This allows us to calculate aggregates over a grouping.

In this sample, Santa wants to know the weights for the different types of toys on his sleigh.

Consider this code:

```csharp
var toys = new[]
{
    new { Category = "Stuffed Animal", Weight = 1.5 },
    new { Category = "Train Set", Weight = 3.0 },
    new { Category = "Stuffed Animal", Weight = 2.0 },
    new { Category = "Puzzle", Weight = 0.8 },
    new { Category = "Train Set", Weight = 2.5 }
};

var totalWeightsByCategory = toys.AggregateBy(
    toy => toy.Category,
    seed: 0.0,
    (total, toy) => total + toy.Weight
);

foreach (var (category, totalWeight) in totalWeightsByCategory)
{
    Console.WriteLine($"{category}: {totalWeight} lbs");
}
```

This is the report of the weights for each of the toy categories:

```text
Stuffed Animal: 3.5 lbs
Train Set: 5.5 lbs
Puzzle: 0.8 lbs
```

There are plenty of other examples out there where you see `AggregateBy` used with sums. But what else can it be used for? Consider this use where we try to find the toy with the longest name in each category:

```csharp
var specificToys = new[]
{
    new { Category = "Stuffed Animal", Name = "Teddy Bear" },
    new { Category = "Stuffed Animal", Name = "Elephant" },
    new { Category = "Train Set", Name = "Steam Engine Deluxe" },
    new { Category = "Puzzle", Name = "3D Castle Puzzle" },
    new { Category = "Train Set", Name = "Freight Train" }
};

var longestToyNamesByCategory = specificToys.AggregateBy(
    toy => toy.Category,
    seed: "",
    (currentLongest, toy) => toy.Name.Length > currentLongest.Length ? toy.Name : currentLongest
);

foreach (var (category, longestName) in longestToyNamesByCategory)
{
    Console.WriteLine($"{category}: {longestName}");
}
```

Notice that the seed is a `string` in this case. That’s because we’re working with `string`s instead of `int`s. The output looks like this:

```text
Stuffed Animal: Teddy Bear
Train Set: Steam Engine Deluxe
Puzzle: 3D Castle Puzzle 
```

Now these have some pretty simple seed types. What if we wanted to find the most expensive toy by category? Consider this code:

```csharp
var pricedToys = new[]
{
    new { Category = "Stuffed Animal", Name = "Teddy Bear", Price = 25.00m },
    new { Category = "Stuffed Animal", Name = "Elephant", Price = 30.00m },
    new { Category = "Train Set", Name = "Steam Engine Deluxe", Price = 50.00m },
    new { Category = "Puzzle", Name = "3D Castle Puzzle", Price = 20.00m },
    new { Category = "Train Set", Name = "Freight Train", Price = 35.00m }
};

var mostExpensiveToysByCategory = pricedToys.AggregateBy(
    toy => toy.Category,
    seed: (Name: "", Price: 0.00m),
    (current, toy) => toy.Price > current.Price ? (toy.Name, toy.Price) : current
);

foreach (var (category, mostExpensive) in mostExpensiveToysByCategory)
{
    Console.WriteLine($"{category}: {mostExpensive.Name} (${mostExpensive.Price})");
}
```

Notice that the seed has both a `string` and a `decimal`. As for the accumulator function, we pass in both the accumulator as well as a toy object. If the toy’s price is greater than the current largest price, then replace the current accumulator with the new toy. Otherwise, that toy is still the largest. The key is the toy’s category – so we’ll get the most expensive toy object for each category.

This is the output:

```text
Stuffed Animal: Elephant ($30.00)
Train Set: Steam Engine Deluxe ($50.00)
Puzzle: 3D Castle Puzzle ($20.00)
```

## Conclusion: Bringing Holiday Cheer to Your Codebase 🎄

.NET 9’s new LINQ features, like `CountBy`, `AggregateBy`, and `Index`, are gifts that keep on giving for developers. Just as St. Nicholas carefully organizes his toys, sleigh, and reindeer to ensure a magical holiday, these features help you streamline your data queries and improve code readability.

Whether you’re tallying toys, weighing sleighs, or finding the most expensive gift, these tools empower you to solve real-world problems with elegance and efficiency. So, unwrap these LINQ features in your next project and make your code shine brighter than Rudolph’s nose! 🎅✨