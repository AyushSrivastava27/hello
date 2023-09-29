---
slug: map-in-golang
title: Golang Maps - Scaler Topics
description: Golang Maps is a collection of unordered pairs of key-value. it provides fast lookups and values that can retrieve, update or delete with the help of keys.
category: Golang
author: Mansi
---

:::section{.abstract}

## Overview
Go maps are a fundamental data structure in the Go programming language. They facilitate key-value pair storage, allowing efficient retrieval, insertion, and deletion operations. Maps ensure the uniqueness of keys and provide fast access, making them useful for tasks like building dictionaries or counting occurrences. A declaration uses the `map[keyType]valueType` syntax. However, maps are not ordered, and iteration order is not guaranteed. In this article, we will dive deep into map in golang. 

:::

:::section{.main}

## Syntax

The syntax for declaring and initializing a map in golang is as follows:
```golang
// Declaration and Initialization
var mapName map[keyType]valueType
mapName = make(map[keyType]valueType)

// OR

mapName := make(map[keyType]valueType)

// Adding elements to the map
mapName[key] = value

// Accessing elements
value := mapName[key]

// Deleting an element
delete(mapName, key)
```

Replace mapName with the desired variable name, keyType with the data type of keys, and valueType with the data type of values you want to store in the map.

:::

:::section{.main}

## How to Create and Initialize Map in Golang?

### Creating Maps Using var and Using Shorthand Syntax

**Syntax**:

```golang
// var a = map[KeyType]ValueType{key1:value1, key2:value2,...}
// b := map[KeyType]ValueType{key1:value1, key2:value2,...}

// The example below demonstrates how to make maps in Go. 
// Take note of the output's and the code's order.

package main

import (
    "fmt"
)

func main() {
    carInfo := map[string]string{"brand": "Ford", "model": "Mustang", "year": "1964"}
    cityRank := map[string]int{"Oslo": 1, "Bergen": 2, "Trondheim": 3, "Stavanger": 4}

    fmt.Printf("Car Info:\t%v\n", carInfo)
    fmt.Printf("City Rank:\t%v\n", cityRank)
}
```

**Output**:
```plaintext
Car Info:	map[brand:Ford model:Mustang year:1964]
City Rank:	map[Bergen:2 Oslo:1 Stavanger:4 Trondheim:3]
```

**Explanation**:

Let's break down the code step by step:

* **package main**: 

    This line declares that the code is a part of the main package, which is necessary for a standalone executable program in Go.
* **import ("fmt")**: 

    The import statement includes the "fmt" package, which provides functions for formatted I/O. This package is used here to print formatted output.
* **func main() { ... }**: 

    This is the main function, which serves as the entry point for execution in a Go program.
* **carInfo := map[string]string{"brand": "Ford", "model": "Mustang", "year": "1964"}**: 

    This line declares and initializes a map named carInfo. It stores information about a car's brand, model, and year. Each key-value pair consists of a string key (e.g., "brand") and a string value (e.g., "Ford").
* **cityRank := map[string]int{"Oslo": 1, "Bergen": 2, "Trondheim": 3, "Stavanger": 4}**: 

    This line declares and initializes a map named cityRank. It stores the ranking of different cities, where the city names (e.g., "Oslo") are keys, and their corresponding rankings (e.g., 1) are integer values.
* **fmt.Printf("Car Info:\t%v\n", carInfo)**: 

    This line uses the Printf function from the "fmt" package to print the contents of the carInfo map. The %v format specifier is used to print the value of the map. The output will show the car's brand, model, and year.
* **fmt.Printf("City Rank:\t%v\n", cityRank)**: 

    Similar to the previous line, this line prints the contents of the cityRank map. It will display the city names and their respective rankings.

### Using make Function

**Syntax**
```golang
var a = make(map[KeyType]ValueType)
b := make(map[KeyType]ValueType)
```

This example shows how to create map in golang using the `make()`function.
```golang
package main

import (
	"fmt"
)

func main() {
	carInfo := make(map[string]string) // The map holds car information
	carInfo["brand"] = "Ford"
	carInfo["model"] = "Mustang"
	carInfo["year"] = "1964"

	cityRanks := make(map[string]int)
	cityRanks["Oslo"] = 1
	cityRanks["Bergen"] = 2
	cityRanks["Trondheim"] = 3
	cityRanks["Stavanger"] = 4

	fmt.Printf("Car Info:\t%v\n", carInfo)
	fmt.Printf("City Ranks:\t%v\n", cityRanks)
}
```

**Output**:
```plaintext
Car Info:	map[brand:Ford model:Mustang year:1964]
City Ranks:	map[Bergen:2 Oslo:1 Stavanger:4 Trondheim:3]
```

**Explanation**:

Let's break down the code step by step:

* The package main statement indicates that this code is part of the main package, which is required for creating executable programs in Go.
* The import "fmt" statement imports the "fmt" package, which provides functions for formatted I/O, like printing to the console.
* The func `main()` is the entry point of the program. It's where the execution of the program begins.
* Inside the main function:
    * The carInfo map is created using the make function. It's a map with keys of type string and values of type string. This map will store information about a car.
    * Key-value pairs are added to the carInfo map using the syntax `mapName[key] = value`. In this case, the brand, model, and year of a car are added.
    * The cityRanks map is created similarly, with keys of type string and values of type int. This map will store ranks of different cities.
    * Rank information is added to the cityRanks map using the key-value pair notation.
* The `fmt.Printf` function is used to print formatted output to the console:
    * The first fmt.Printf statement prints the contents of the carInfo map, using the %v format verb to display the map.
    * The second fmt.Printf statement prints the contents of the cityRanks map in a similar manner.
* The program will output the information stored in the carInfo and cityRanks maps, providing a clear view of how maps store key-value pairs and allow retrieval of values based on keys.

:::

:::section{.main}

## How to Iterate over a Map?

You can use range to iterate over maps.
This example shows how to iterate over the elements in a map. Take note of the output's element order.
```golang
package main

import (
	"fmt"
)

func main() {
	data := map[string]int{"first": 1, "second": 2, "third": 3, "fourth": 4}

	for key, val := range data {
		fmt.Printf("%s : %d, ", key, val)
	}
}
```

**Output**:
```plaintext
first : 1, second : 2, third : 3, fourth : 4, 
```

**Explanation**:

Here's an explanation of each part of the code:

* **package main**: 

    This line indicates that this Go file belongs to the main package, which is the entry point for a Go executable program.
* **Import Statement**: 

    The import block allows you to include necessary packages from the Go standard library. In this case, the "fmt" package is imported, which provides functions for formatted input/output.
* **func main()**: 

    This is the main function where the execution of the program starts.
* **data := map[string]int{"first": 1, "second": 2, "third": 3, "fourth": 4}**: 

    This line declares and initializes a map named data. The map has string keys and integer values. It contains four key-value pairs: "first" mapped to `1`, "second" mapped to `2`, "third" mapped to `3`, and "fourth" mapped to `4`.
* **for key, val := range data { ... }**: 

    This loop iterates through each key-value pair in the data map using the range keyword. During each iteration, the key variable holds the current key, and the val variable holds the corresponding value.
* **fmt.Printf("%s : %d, ", key, val)**: 

    Inside the loop, this line uses the Printf function from the "fmt" package to print the current key and value in a formatted manner. %s is a placeholder for a string, and %d is a placeholder for an integer. The values of key and val are substituted into the placeholders to create the output. The , adds a comma after each printed key-value pair.

It effectively prints each key and its corresponding value from the data map in a comma-separated format.

:::

:::section{.main}

## How to Add key-value Pairs in the Map?

In maps, you are allowed to add key-value pairs using the following syntax to the initialized map:
```golang
map_name[key]=value
```

If you try to add a key to an existing map, it will simply replace or update the key's value with the new value.

```golang
package main

import "fmt"

func main() {
    // Creating and initializing a map
    animalMap := map[int]string{
        90: "Dog",
        91: "Cat",
        92: "Cow",
        93: "Bird",
        94: "Rabbit",
    }

    fmt.Println("Original map: ", animalMap)

    // Adding new key-value pairs to the map
    animalMap[95] = "Parrot"
    animalMap[96] = "Crow"
    fmt.Println("Map after adding new key-value pairs:\n", animalMap)

    // Updating values in the map
    animalMap[91] = "Pig"
    animalMap[93] = "Donkey"
    fmt.Println("\nMap after updating values:\n", animalMap)

    // Iterating through the map
    for key, value := range animalMap {
        fmt.Printf("%d : %s\n", key, value)
    }
}
```

**Output**:
```plaintext
Original map:  map[90:Dog 91:Cat 92:Cow 93:Bird 94:Rabbit]
Map after adding new key-value pairs:
 map[90:Dog 91:Cat 92:Cow 93:Bird 94:Rabbit 95:Parrot 96:Crow]

Map after updating values:
 map[90:Dog 91:Pig 92:Cow 93:Donkey 94:Rabbit 95:Parrot 96:Crow]
92 : Cow
93 : Donkey
94 : Rabbit
95 : Parrot
96 : Crow
90 : Dog
91 : Pig
```

**Explanation**:

This Go code demonstrates map usage. It initializes an `animalMap` with key-value pairs representing animals. New entries are added for "Parrot" and "Crow". Values for "Cat" and "Bird" are updated to "Pig" and "Donkey" respectively. The loop iterates through the map, printing each key-value pair. This showcases map creation, modification, and iteration in Go.

:::

:::section{.main}

## How to Retrieve a Value Related to a Key in the Maps?

The following syntax can be used to obtain a value using a key in maps:

**Syntax**:
```golang
map_name[key]
```

It will return the map's zero value or nil if the key is missing from the specified map. It will also return the value associated with that key if it is present in the provided map.

**Example**:
```golang
package main

import "fmt"

func main() {
	// Initialize a map with animal names and their corresponding codes
	animalMap := map[int]string{
		100: "Elephant",
		101: "Lion",
		102: "Giraffe",
		103: "Tiger",
		104: "Kangaroo",
	}

	// Display the original map
	fmt.Println("Original animal map:", animalMap)

	// Retrieve values using keys
	code1 := 100
	code2 := 103
	animal1 := animalMap[code1]
	animal2 := animalMap[code2]

	// Display retrieved values
	fmt.Printf("Animal with code %d: %s\n", code1, animal1)
	fmt.Printf("Animal with code %d: %s\n", code2, animal2)
}
```

**Output**:
```plaintext
Original animal map: map[100:Elephant 101:Lion 102:Giraffe 103:Tiger 104:Kangaroo]
Animal with code 100: Elephant
Animal with code 103: Tiger
```

**Explanation**:

This Go code demonstrates the use of map in golang. It initializes an animalMap map with integer keys representing animal codes and corresponding string values for animal names. After displaying the original map, it retrieves animal names using specific codes (`100` and `103`) and prints them. The code showcases how maps work in Go, allowing key-based data retrieval and storage. It also highlights the flexibility of maps in associating values with unique keys.

:::

:::section{.main}

## How to Check the Existence of the Key in the Map?

In maps, you can use the following syntax to determine whether a key is present or not:

```golang
// With value
// It will gives the value and check result
value, check_variable_name:= map_name[key]

or

// Without value using the blank identifier
// It will only give check result
_, check_variable_name:= map_name[key]
Here, if the check_variable_name value is true, the key is present in the supplied map; otherwise, if the check_variable_name value is false, the key is not present in the given map. 
```

**Example**:
```golang
package main

import "fmt"

func main() {
	animalSounds := map[string]string{
		"dog":    "Woof",
		"cat":    "Meow",
		"cow":    "Moo",
		"bird":   "Chirp",
		"rabbit": "Squeak",
	}

	fmt.Println("Sounds of various animals: ", animalSounds)

	soundDog, dogExists := animalSounds["dog"]
	fmt.Println("\nIs 'dog' sound known:", dogExists)
	fmt.Println("Sound:", soundDog)

	_, birdExists := animalSounds["bird"]
	fmt.Println("\nIs 'bird' sound known:", birdExists)
}
```

**Output**:
```golang
Sounds of various animals:  map[bird:Chirp cat:Meow cow:Moo dog:Woof rabbit:Squeak]

Is 'dog' sound known: true
Sound: Woof

Is 'bird' sound known: true
```

**Explanation**:

This Go code demonstrates the usage of maps for associating animal names with their corresponding sounds. The map `animalSounds` is initialized with key-value pairs representing animals and their sounds. The program then checks if the key "dog" exists in the map, retrieving the associated sound and indicating its presence. Similarly, it checks for the existence of the key "bird". The code showcases map usage, key existence checks using the comma-ok idiom, and value retrieval.

:::

:::section{.main}

## How to Delete Keys from the Map?

You can use the `delete()` function in maps to remove the key that is stored there. It is a built-in function with no return value and does nothing if the key is missing from the provided map. When using this function, you only need to pass the key and the map you wish to remove from the map.

**Syntax**: 

```golang
delete(map_name, key)
```

**Example**:
```golang
package main

import "fmt"

func main() {
    // Creating and initializing a map
    animalMap := map[int]string{
        90: "Dog",
        91: "Cat",
        92: "Cow",
        93: "Bird",
        94: "Rabbit",
    }

    fmt.Println("Original map: ", animalMap)

    // Deleting keys using delete function
    delete(animalMap, 90)
    delete(animalMap, 93)

    fmt.Println("Map after deletion: ", animalMap)
}
```

**Output**:
```plaintext
Original map:  map[90:Dog 91:Cat 92:Cow 93:Bird 94:Rabbit]
Map after deletion:  map[91:Cat 92:Cow 94:Rabbit]
```

**Explanation**:

This Go program demonstrates key deletion in a map. An initial map called `animalMap` is created and populated with integer keys representing animal IDs and corresponding string values representing animal names. The program then uses the `delete` function to remove entries with keys 90 and 93. Finally, it prints the original and modified maps after deletion, showcasing the removal of the specified key-value pairs.

:::

:::section{.main}

## Modifying Map

Maps are known to be of the reference type. As a result, both maps still make reference to the same underlying data structure when we assign an existing map to a new variable. As a result, when we update one map, another map will also update.

**Example**:
```golang
package main

import (
	"fmt"
	"reflect"
)

func main() {
	// Creating and initializing a map
	originalMap := map[int]string{
		90: "Dog",
		91: "Cat",
		92: "Cow",
		93: "Bird",
		94: "Rabbit",
	}
	fmt.Println("Original map: ", originalMap)

	// Create a copy of the map
	copiedMap := make(map[int]string)
	for key, value := range originalMap {
		copiedMap[key] = value
	}

	// Perform modification on copiedMap
	copiedMap[96] = "Parrot"
	copiedMap[98] = "Pig"

	// Display modified map and check if the original map is unchanged
	fmt.Println("Copied map with modifications: ", copiedMap)
	fmt.Println("\nOriginal map (unchanged): ", originalMap)

	// Check if the original map and copied map are distinct
	if reflect.DeepEqual(originalMap, copiedMap) {
		fmt.Println("\nThe original map and copied map are the same.")
	} else {
		fmt.Println("\nThe original map and copied map are distinct.")
	}
}
```

**Output**:

```plaintext
Original map:  map[90:Dog 91:Cat 92:Cow 93:Bird 94:Rabbit]
Copied map with modifications:  map[90:Dog 91:Cat 92:Cow 93:Bird 94:Rabbit 96:Parrot 98:Pig]

Original map (unchanged):  map[90:Dog 91:Cat 92:Cow 93:Bird 94:Rabbit]
```

The original map and the copied map are distinct.

**Explanation**:

This Go code initializes an original map with integer keys and string values. It then creates a copy of this map and modifies the copy by adding new key-value pairs. Importantly, it demonstrates that modifying the copy doesn't impact the original map. The code also checks the equality of both maps using the `reflect.DeepEqual` function and confirms that they are distinct. This illustrates the concept of map assignment, modification, and the independence of copied maps from the original data structure.

:::

:::section{.main}

## Copying One Map to Another (Using for Loop, Copy Keyword doesn’t Work on Map)

Using the for loop that the Go language offers, you can copy a map from one map to another map in Map. We retrieve the index value along with the element in a for loop and assign it to another map.

**Syntax**:
```golang
for key, value := range originalMap{
}
```
Let us discuss this concept with the help of the example:
```golang
package main

import "fmt"

func main() {

	// Creating and initializing a map
	map1 := map[int]string{
		90: "Dog",
		91: "Cat",
		92: "Cow",
		93: "Bird",
		94: "Rabbit",
	}

	// Creating and initializing an empty map
	map2 := make(map[string]int)

	/* Copy Content from Map1 to Map2 */
	for key, value := range map1 {
		map2[value] = key
	}

	fmt.Println("Copied Map:", map2)
}
```

**Output**:
```plaintext
Copied Map: map[Bird:93 Cat:91 Cow:92 Dog:90 Rabbit:94]
```

**Explanation**:

The given Go code demonstrates copying elements from one map (`map1`) to another map (`map2`). It initializes `map1` with integer keys and corresponding string values. An empty map `map2` is created. Through a loop, the code iterates over the key-value pairs in `map1`, copying the values as keys and the keys as values into `map2`. This effectively swaps the roles of keys and values between the two maps. Finally, the code prints the content of `map2`, showing the copied mapping where strings are now keys and integers are values.

:::

:::section{.summary}

## Conclusion 
Here are some concluding points about map in golang:

1. **Key-Value Data Structure:** Maps in Go provide a powerful way to store key-value pairs, allowing efficient lookup, insertion, and deletion operations.
2. **Declaration and Initialization:** Maps are created using the `make()` function or using literal syntax. For example: `mapName := make(map[keyType]valueType)`.
3. **Key Uniqueness:** Maps ensure the uniqueness of keys. Duplicate keys are not allowed; each key can map to at most one value.
4. **Dynamic Size:** Maps can dynamically grow as elements are added. They don't need to have a fixed size declared upfront.
5. **Fast Access:** Maps provide fast access to values based on their keys. This makes them suitable for tasks like caching, indexing, and building lookup tables.

Overall, maps in Go provide a flexible and efficient way to manage key-value relationships, making them a cornerstone of many Go programs.

:::