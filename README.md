# iOS applicationsutveckling för iPhone och iPad style guide

## Table of Contents

* [Generelt](#generelt)
  * [DRY](#dry)
  * [Hårdkoding](#hårdkoding)
  * [Gruppera kod](#gruppera-kod)
  * [Namn](#namn)
  * [Indentering](#indentering)
  * [Måsvingar](#måsvingar)
* [Objective-C](#objective-c)
  * [Properties](#properties)
  * [Undvik C](#undvik-c)
* [Swift](#swift)
  * [Optionals](#optionals)
  * [Higher order functions](#higher-order-functions)
  * [Struct vs Class vs Enum](#struct-vs-class-vs-enum)
  
## Generelt

### DRY

DRY Står för 'don't reapeat yourself' vilket är ett bra regel att ha när man skriver kod. Detta betyder att ingen eller minimal repetion och hårdkodning

**Dåligt exempel:**

*Objective-C*

```objective-c
NSString *name1 = @"Cenny";
NSString *name2 = @"Carl";
NSString *name3 = @"Pär";

NSLog(@"%@!", name1);
NSLog(@"%@!", name2);
NSLog(@"%@!", name3);

```

**Bra exempel:**

*Objective-C*

```objective-c
NSArray *names = @[@"Cenny", @"Carl", @"Pär”];   

for (NSString *name in names) {
	NSLog(@"%@!", name);
}
```

*Swift*

```swift
let names = ["Cenny", "Carl", "Pär”]

names.forEach { name in
	print("\(name)!")
}
```

Alla exemplen ovan genererar nedanstående text i loggen men de två bra exemplen gör samma sak på färre rader kod och är och lättare att ändra om ett eller flera namn ska läggas till/tas bort.

	Cenny!
	Carl!
	Pär!

### Hårdkoding

**Dåligt exempel:**

*Objective-C*

```objective-c
NSArray *names = @[@"Cenny", @"Carl", @"Pär”];   

for (int i = 0; i < 3; i++) {
	NSLog(@"%@!", names[i]);
}
```

**Bra exempel:**

*Objective-C*

```
for (NSString *name in names) {
	NSLog(@"%@!", name);
}
```

*Swift*

```swift
let names = ["Cenny", "Carl", "Pär”]

names.forEach { name in
	print("\(name)!")
}
```


### Gruppera kod

### Namn

### Indentering

### Måsvingar

## Objective-C

### Properties

### Undvik C

## Swift

### Optionals

### Higher order functions

### Struct vs Class vs Enum
