# iOS applicationsutveckling för iPhone och iPad style guide

## Table of Contents

* [Generellt](#generellt)
  * [DRY](#dry)
  * [Hårdkodning](#hårdkodning)
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

## Generellt

### DRY

DRY Står för "Don't Repeat Yourself" vilket är en bra regel att ha när man skriver kod. Detta betyder att försöka ha ingen eller minimal repetition och hårdkodning

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
let names = ["Cenny", "Carl", "Pär"]

names.forEach { name in
	print("\(name)!")
}
```

Alla exemplen ovan genererar nedanstående text i loggen men de två bra exemplen gör samma sak på färre rader kod och är och lättare att ändra om ett eller flera namn ska läggas till/tas bort.

	Cenny!
	Carl!
	Pär!

### Hårdkodning

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

```objective-c
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

### Namngivning
Det är viktigt att namnge variabler, metoder, klasser och andra saker i sin kod. Ofta finns det en konvention för språket om hur detta ska göras. I Swift och Objective-C är konventionen följande:

- Klasser ska börja med stor bokstav och vid flera ord ska camel case användas.
- Metoder och funktioner ska börja med liten bokstav och vid flera ord ska camel case användas.
- Enums och dess värden ska börja med stor bokstav och vid flera ord ska camel case användas.
- Variabler ska börja med liten bokstav och vid flera ord ska camel case användas.

Utöver detta så är det viktigt att namn är beskrivande av vad objektet, klassen eller metoden är eller ska göra. Dålig namngivning kan leda till otydligheter om koden.

**Dåligt exempel:**

*Objective-C*

```objective-c
@implementation simpleClass
+ (void) foo:(NSarray) bar {
  for (NSString *mystring in bar) {
    NSLog(@"%@!", mystring);
  }
}
@end

NSArray *n = @[@"Cenny", @"Carl", @"Pär"];

[simpleClass foo:n];
```

**Bra exempel**

*Objective-C*

```objective-c
@implementation SimpleClass
+ (void) printNames:(NSarray) names {
  for (NSString *name in names) {
    NSLog(@"%@!", s);
  }
}
@end

NSArray *names = @[@"Cenny", @"Carl", @"Pär"];

[SimpleClass printNames:names];
```



### Indentering

### Måsvingar

## Objective-C

### Properties

### Undvik C

## Swift

### Optionals

### Higher order functions

### Struct vs Class vs Enum
