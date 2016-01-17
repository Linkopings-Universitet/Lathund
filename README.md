# iOS applicationsutveckling för iPhone och iPad style guide

## Table of Contents

* [Generellt](#generellt)
  * [DRY](#dry)
  * [Hårdkodning](#hårdkodning)
  * [Gruppera kod](#gruppera-kod)
  * [Namngivning](#namngivning)
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

Hårdkoning (även kallat statisk lösning) är när man löst ett problem för endast ett specifikt scenario. Om du har en lösning för hur du kan göra x tre gånger men inte två eller fyra gånger så har du en väldigt statisk lösning på problemet. Detta kan leda till repetition och buggar.

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
+ (void) foo:(NSarray *) bar {
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
+ (void) printNames:(NSarray *) names {
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

Många språk har konventioner om var måsvingarna ska placeras och det är rekommenderat att följa dessa konventioner då det är det som förväntas av din kod. Om du skulle vara ovetande av vilken konvention som gäller eller det inte finns någon så är det viktig att du är konsekvent med hur du placerar. Det är också viktigt att måsvingarna är rätt indenterade, den avslutade måsvingen ska va i linje med metoden/loopen/if/osv början.

**Dåligt exempel:**

*Objective-C*

```objective-c
@implementation SimpleClass
+ (void) printNames:(NSarray *) names 
{
  for (NSString *name in names) {
    NSLog(@"%@!", s);
}
}
@end
```

**Bra exempel**

*Objective-C*

```objective-c
@implementation SimpleClass
+ (void) printNames:(NSarray *) names {
  for (NSString *name in names) {
    NSLog(@"%@!", s);
  }
}
@end
```

## Objective-C

### Properties

### Undvik C

## Swift

### Optionals

### Higher order functions

### Struct vs Class vs Enum
