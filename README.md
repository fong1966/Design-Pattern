# Design Pattern for Dart

* 設計模式是拿來解決問題，而非拿來炫技，過度使用可能會引起反效果，搞亂所有的 code 也說不定。

* 但合理且成功的使用設計模式，可以最大化的有效解決問題，因為這些模式都是前人不斷尋找解決辦法而產生的。
* 共有三種設計模式 : 
  * [Creational Design Pattern](#種類一-Creational-Design-Pattern) 注重如何初始化一個或一群物件。
    * Factory, Builder, Prototype, Singleton, ...
  * [Structural Design Pattern](#種類二-Structural-Design-Pattern) 注重實體之間怎麼互相運用。以「組合」取代「繼承」。
    * Decorator, Adapter, Composite, Facade, Proxy, ...
  * [Behavioral Design Pattern](#種類三-Behavioral-Design-Pattern) 分配每個物件的責任，不只單純創建，而是建立溝通方式。
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
> 幫助串聯物件，並且在 Request 時從最前面的物件往後找起，直到找到可以符合條件的物件。
> 假設你有 A, B, C 三個帳戶，要求消費時由 A 開始扣款，如果 A 不夠再去找 B , C 。

何時使用
> 如果有多個物件可以用來處理 request ，並且想要他們有優先順序時。

💎[Code](lib/Behavioral/ChainOfResponsibility.dart)

---
### 🥨 Command
目的
> 想像你是 client ，服務員是 invoker ，主廚是 receiver。
> Command 將 Actions 封裝在物件中，提供方法去解耦 client 和 receiver 。

何時使用
> 需要記錄 Request 的歷史時，需要實作 callback 和 undo 時。

💎[Code](lib/Behavioral/Command.dart)

---
### 🍦 Iterator
目的
> 在不暴露內部邏輯情況下，按順序將集合物件顯示出來。

何時使用
> 想要統一 Traversal 方法，或想支援多層 Traversal 時。

💎[Code](lib/Behavioral/Iterator.dart)

---
### 🍨 Mediator
目的
> 新增一個中介者 (mediator) 來控制兩個物件的交流，進而減少兩者的耦合。

何時使用
> 當有兩個物件要溝通時，溝通過程十分複雜，需要有效管理時。

💎[Code](lib/Behavioral/Mediator.dart)

---
### 🍬 Memento
目的
> 在不影響封裝的情況下，讓物件能夠 Restore 到某一個狀態。

何時使用
> 當你需要暫時將物件存下 Snapshot 以便在未來方便復原。

💎[Code](lib/Behavioral/Memento.dart)

---
### 🍮 Observer
目的
> 定義出一個一對多的物件關係，當物件改變狀態時，訂閱他的對象將全部收到更新。

何時使用
> 當你的物件之間有一方依賴於另一方，並且在一方改變時想要即時更新其他相依對象時。

💎[Code](lib/Behavioral/Observer.dart)

---
### 🍩 Visitor
目的
> 定義新的 Operation 給物件表現，而不改變原本的物件。

何時使用
> 當你想維持 class 不變，但又常常需要幫他加入新的 Operation 。

💎[Code](lib/Behavioral/Visitor.dart)

---
### 🍻 Strategy
目的
> 定義一群相關的策略並將每個策略封裝起來，使他們可以在不同情況下交互使用。

何時使用
> 當你需要依情況使用表面相差不大但方法不同的物件，並且想把每個物件的複雜方法隱藏起來時。

💎[Code](lib/Behavioral/Strategy.dart)

---
### 🍰 State
目的
> 讓物件的行為根據其內部 "state" 的改變而改變，看起來會像物件自己改變了他的 class 。

何時使用
> 當你的物件有非常多條件變數時，想讓物件因這些條件而改變。

💎[Code](lib/Behavioral/State.dart)

---
### 🥝 Template
目的
> 定義好介面後，將一些屬性交給實作的物件決定。且該決定不會影響原本介面的架構。

何時使用
> 當你有不變的架構，但想要有不同的行為時。交給 SubClass 來擴充即可。

💎[Code](lib/Behavioral/Template.dart)

---

### For more, please visit:
* [iluwatar/java-design-patterns](https://github.com/iluwatar/java-design-patterns)
* [kamranahmedse/design-patterns-for-humans](https://github.com/kamranahmedse/design-patterns-for-humans)