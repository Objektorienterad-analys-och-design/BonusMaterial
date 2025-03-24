# Introduktion till TypeScript - Del 1

## Vad är TypeScript?

TypeScript är ett programmeringsspråk utvecklat av Microsoft som bygger på JavaScript. Det lägger till **optional static typing** till JavaScript, vilket hjälper till att upptäcka fel tidigare i utvecklingsprocessen.

TypeScript är en **superset** av JavaScript, vilket betyder att all giltig JavaScript-kod även är giltig TypeScript-kod. TypeScript-kod kompileras sedan till vanlig JavaScript som kan köras i webbläsare, Node.js eller andra JavaScript-miljöer.

```typescript
// TypeScript lägger till typannoteringar till JavaScript
let message: string = "Hello, TypeScript!";
console.log(message);
```

## Varför TypeScript?

TypeScript skapades för att göra det enklare att utveckla och underhålla större JavaScript-applikationer:

1. **Upptäck fel tidigt** - Kompilatorn hittar många vanliga fel innan koden körs
2. **Bättre verktygsintegrering** - Ger bättre autocomplete och IntelliSense
3. **Ökad produktivitet** - Gör det enklare att refaktorera kod
4. **Bättre dokumentation** - Typer fungerar som dokumentation av koden

## Grundläggande typer i TypeScript

```typescript
// Grundläggande typer
let isDone: boolean = false;
let decimal: number = 6;
let color: string = "blue";
let list: number[] = [1, 2, 3];
let tuple: [string, number] = ["hello", 10];

// Enum
enum Color {Red, Green, Blue}
let c: Color = Color.Green;

// Any - för värden där vi inte vet typen
let notSure: any = 4;
notSure = "maybe a string";
notSure = false; // också OK

// Void - används främst för funktioner som inte returnerar något
function warnUser(): void {
    console.log("This is a warning message");
}
```

## Funktioner i TypeScript

```typescript
// Parameter- och returtyper
function add(x: number, y: number): number {
    return x + y;
}

// Optional parameter
function buildName(firstName: string, lastName?: string): string {
    if (lastName) {
        return firstName + " " + lastName;
    } else {
        return firstName;
    }
}

// Default parameter
function greeting(name: string = "Guest"): string {
    return `Hello, ${name}!`;
}
```

## TypeScript vs Java: Syntax-jämförelse

### 1. Deklaration av variabler

**Java:**
```java
String name = "John";
int age = 30;
boolean isActive = true;
```

**TypeScript:**
```typescript
let name: string = "John";
let age: number = 30;
let isActive: boolean = true;

// TypeScript kan också göra type inference
let name = "John";  // TypeScript förstår att detta är en string
```

### 2. Funktioner

**Java:**
```java
public int add(int a, int b) {
    return a + b;
}
```

**TypeScript:**
```typescript
function add(a: number, b: number): number {
    return a + b;
}
```

### 3. Klasser

**Java:**
```java
public class Person {
    private String name;
    private int age;
    
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
    
    public String getName() {
        return name;
    }
    
    public void setName(String name) {
        this.name = name;
    }
}
```

**TypeScript:**
```typescript
class Person {
    private name: string;
    private age: number;
    
    constructor(name: string, age: number) {
        this.name = name;
        this.age = age;
    }
    
    getName(): string {
        return this.name;
    }
    
    setName(name: string): void {
        this.name = name;
    }
}
```

### 4. Arrays

**Java:**
```java
String[] names = {"Alice", "Bob", "Charlie"};
int[] numbers = new int[5];
```

**TypeScript:**
```typescript
let names: string[] = ["Alice", "Bob", "Charlie"];
let numbers: number[] = new Array(5);
```

## Grundläggande regler för TypeScript

1. **Type annotations är valfria** - TypeScript kan ofta härleda typen:
   ```typescript
   let name = "John";  // TypeScript vet att detta är en string
   ```

2. **JavaScript är giltig TypeScript** - All JavaScript-kod är även giltig TypeScript-kod.

3. **Types kontrolleras vid kompilering** - Inte vid runtime.

4. **TypeScript kompileras till JavaScript** - Kod med typer översätts till JavaScript utan typer.

5. **Typer kan vara specifika eller flexibla** - Från exakta typer till mycket flexibla:
   ```typescript
   let exactType: number = 10;
   let flexibleType: any = "anything";
   ```

## Komma igång med TypeScript

För att börja använda TypeScript:

1. Installera TypeScript via npm:
   ```
   npm install -g typescript
   ```

2. Skapa en TypeScript-fil, till exempel `hello.ts`:
   ```typescript
   function greet(name: string): string {
       return `Hello, ${name}!`;
   }
   console.log(greet("World"));
   ```

3. Kompilera till JavaScript:
   ```
   tsc hello.ts
   ```

4. Kör den kompilerade JavaScript-filen:
   ```
   node hello.js
   ```

## Sammanfattning

TypeScript erbjuder:
- JavaScript plus type checking
- Enklare verktygsintegrering och autocomplete
- Bättre felhantering under utveckling
