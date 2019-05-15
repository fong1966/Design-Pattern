# Design Pattern for Dart

* 設計模式是拿來解決問題，而非拿來炫技，過度使用可能會引起反效果，搞亂所有的 code 也說不定。

* 但合理且成功的使用設計模式，可以最大化的有效解決問題，因為這些模式都是前人不斷尋找解決辦法而產生的。
* 共有三種設計模式 : 
  * Creational Design Pattern 注重如何初始化一個或一群物件。
    * Factory, Builder, Prototype, Singleton, ...
  * Structural Design Pattern 注重實體之間怎麼互相運用。以「組合」取代「繼承」。
    * Decorator, Adapter, Composite, Facade, Proxy, ...
  * Behavioral Design Pattern 分配每個物件的責任，不只單純創建，而是建立溝通方式。
    * Strategy, Observer, State, Command, Iterator, Template, ...



## 種類一 Creational Design Pattern
### 🍕 Simple Factory
目的
> 給 Client 產生東西的方法，但不暴露產生的邏輯。

何時使用
> 要產生的物件需要比較多一些邏輯時，避免在產生多個物件造成太多 Code 重複。

💎[Code](lib/Creational/SimpleFactory.dart)

---
### 🍔 Factory Method
目的
> 建立 Interface ，但給 SubClass 自行決定要如何初始化。將初始化延至 SubClass。

何時使用
> 當 SubClass 有共用的屬性，但需要在 Runtime 時動態決定一些事情。即 Client 不需知道 SubClass 的 Detail。

💎[Code](lib/Creational/FactoryMethod.dart)

---
### 🍟 Abstract Factory
目的
> 建立一個 Interface 囊括所有相關物件的家族，且不暴露他們的 Class 。

何時使用
> 當有一些相依物件需要維護，且產生邏輯有一定的複雜程度時。

💎[Code](lib/Creational/AbstractFactory.dart)

---
### 🌭 Builder
目的
> 將複雜的物件拆開成每個零件，像遊戲角色一樣，有職業、性別、頭髮等等。

何時使用
> 當一個物件有很多分部，並且想避免"伸縮建構"時。 
> Character(name, hair, profession, ......) 全部擠在一個 constructor 中。
> 跟 Factory 不同的是，Factory 通常一步就可以生產，而 Builder 需要多步建構。

💎[Code](lib/Creational/Builder.dart)

---
### 🍿 Prototype
目的
> 利用 Clone 已有物件的方式創建新的物件。

何時使用
> 當要創建一個物件非常類似於現有物件時。

💎[Code](lib/Creational/Prototype.dart)

---
### 🥞 Singleton
目的
> 確保建立出來的物件只會有一個實例，並且提供 client 一個全域變數來使用他。

何時使用
> 當你想確保物件不會被重複產生時。

💎[Code](lib/Creational/Singleton.dart)

---

## 種類二 Structural Design Pattern
### 🍙 Adapter
目的
> 將一個 Interface 轉換成另一個 Interface 。讓原本不可能一起工作的 Class 變成可能。

何時使用
> 當你想使用現有 Class 但他的 interface 不符合你的規定。

💎[Code](lib/Structural/Adapter.dart)

---
### 🍣 Bridge
目的
> 以組合取代繼承，可以避免繼承過度。

何時使用
> 當網站有多個頁面有不同主題時，要把每個頁面都繼承多個主題 ? 還是把頁面跟主題結合起來 ?

💎[Code](lib/Structural/Bridge.dart)

---
### 🍖 Composite
目的
> 將相同 interface 但不同責任的物件，集中到樹狀結構來管理。

何時使用
> 當有一群類似的物件，想要集中管理時。

💎[Code](lib/Structural/Composite.dart)

---
### 🍤 Decorator
目的
> 能夠動態的加入責任給任一物件。提供比繼承更有彈性的擴充。

何時使用
> 當要動態加入的責任過多，用繼承會變得很好笑的時候。

💎[Code](lib/Structural/Decorator.dart)

---
### 🥙 Facade
目的
> 創造一個 High-Level 的介面，來讓底下的系統更好被使用。

何時使用
> 當你有一堆小的子系統，要一個一個操作很繁雜的時候。

💎[Code](lib/Structural/Facade.dart)

---
### 🥗 FlyWeight
目的
> 利用共享來有效處理大量相似的物件，進而最小化記憶體的用量。

何時使用
> 當有大量物件要使用時，或是處理物件是很花費記憶體時。

💎[Code](lib/Structural/FlyWeight.dart)

---
### 🥣 Proxy
目的
> 利用代理模式可以讓一個 Class 來代理實現另一個 Class 的功能

何時使用
> 當一個 Class 有較多元及複雜的功能需要另一個 Class 的幫忙來實現時。

💎[Code](lib/Structural/Proxy.dart)

---

## 種類三 Behavioral Design Pattern
### 🍛 Chain of Responsibility
目的
> 

何時使用
> 

💎[Code](lib/Behavioral/ChainOfResponsibility.dart)

---
### 🥨 Command
目的
> 

何時使用
> 

💎[Code](lib/Behavioral/Command.dart)

---
### 🍦 Iterator
目的
> 

何時使用
> 

💎[Code](lib/Behavioral/Iterator.dart)

---
### 🍨 Mediator
目的
> 

何時使用
> 

💎[Code](lib/Behavioral/Mediator.dart)

---
### 🍬 Memento
目的
> 

何時使用
> 

💎[Code](lib/Behavioral/Memento.dart)

---
### 🍮 Observer
目的
> 

何時使用
> 

💎[Code](lib/Behavioral/Observer.dart)

---
### 🍩 Visitor
目的
> 

何時使用
> 

💎[Code](lib/Behavioral/Visitor.dart)

---
### 🍻 Strategy
目的
> 

何時使用
> 

💎[Code](lib/Behavioral/Strategy.dart)

---
### 🍰 State
目的
> 

何時使用
> 

💎[Code](lib/Behavioral/State.dart)

---
### 🥝 Template
目的
> 

何時使用
> 

💎[Code](lib/Behavioral/Template.dart)