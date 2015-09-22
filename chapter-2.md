###Chapter 2: Meaningful Names

###### # Use intention-revealing names
The name of a var, function, or class, should tell you `WHY IT EXISTS`, `WHAT IT DOES`, AND `HOW IT IS USED`.
If a name requires a comment, then the name doesn't reveal its intent.

> int elapsedTimeInDays;
> int daysSinceCreation;
> int daysSinceModification;
> int fileAgeInDays;

```
public List<Cell> getFlaggedCells() {
  List<Cell> flaggedCells = new ArrayList<Cell>();
  for (Cell cell : gameBoard)
    if (cell.isFlagged())
      flaggedCells.add(cell);
  return flaggedCells;
}
```

###### # Avoid disinformation
In order to refer to a grouping of accounts, use `accountGroup`, `bunchOfAccounts` or just plain `accounts`. Prevent to use `accountList` unless it's actually a `List` (datatype).

###### # Make meaningful distinctions
Noise works are another meaninglesss distinction.
E.g: `Product`, `ProductInfo`, `ProductData`.
Making the names different without making them mean anything different. `Info` and `Data` are indistinct noise words like `a, an, the`.

Distinguish names in such a way that the reader knows what the differences offer.

###### # Use pronounceable names
Making your names pronounceable.
E.g:
```
class Customer {
  private Date generationTimestamp;
  private Date modificationTimestamp;;
  private final String recordId = "102";
/* ... */
};
```

###### # Use searchable names
If a variable or constant might be seen or used in mulitiple places in a body of code, it is imperative to give it a search-friendly name.

Single-letter names and numeric constants have a particular problem in that they are not easy to locate across a body of text.

A single-letter names can ONLY be used as local variables inside short methods.
> The length of a name should correspond to the size of its scope.

###### # Avoid encodings

###### Member prefixes
Don't need to prefix member variables with m_ anymore - classes and function should be small enough.

###### # Interfaces and implementations

###### # Avoid mental mapping
Readers shouldn't gave to mentally translate your names into others names they already know.
> Clearity is king

###### # Class names
Classes and objects should have `noun` or `noun phrase` (not ~~VERB~~) names like
- Customer
- Processor
- Data
- Info

###### # Method names
Methods should have `verb` or `verb phrase` names like
- postPayment
- deletePage
- save

Accessors, mutators, and predicates should be named for their value and prefixed w/ `get`, `set`, and `is`.

> string name = employee.getName();
> customer.setName('Duc');
> if (payment.isPaid()) ...

When constructors are overloaded (with arguments), use static factory methods w/ names that describe the arguments.
> Complex fulcumPoint = Complex.FromRealNumber(23.0);
> Better than 
> ~~Complex fulcumPoint = new Complex(23.0);~~

###### # Don't be cute
Choose clarity over entertainment value.
Say what you mean. Mean what you say.

###### # Pick one word per Concept
Pick one word for one abstract concept and stick with it.
For instance, `fetch`, `retrieve`, and `get`.
A consistent lexicon is a great boon to the programmers who must use your code.

###### # Don't pun
Avoid using the same word for two purposes. Using  the same term for two different ideas is essentially a pun.















