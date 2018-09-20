---
title: Объявление объекта ссылочного класса CLR | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- types [C++], reference types
- reference types, CLR
ms.assetid: 6d64f746-3715-4948-ada3-88859f4150e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f3e8ec6407e12d0c26331d45dc1659277feed016
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444584"
---
# <a name="declaration-of-a-clr-reference-class-object"></a>Объявление объекта ссылочного класса в среде CLR

Синтаксис объявления и создания экземпляра объекта ссылочного класса типа отличается от управляемых расширений для C++ в Visual C++.

В управляемых расширениях объекта ссылочного класса типа объявлен с помощью синтаксиса указателя ISO-C++, с помощью необязательного использования `__gc` ключевое слово слева от типа "звезда" (`*`). Например ниже приведены различные ссылки на объявлений объектов типа класса в синтаксисе управляемых расширений.

```
public __gc class Form1 : public System::Windows::Forms::Form {
private:
   System::ComponentModel::Container __gc *components;
   Button __gc *button1;
   DataGrid __gc *myDataGrid;
   DataSet __gc *myDataSet;

   void PrintValues( Array* myArr ) {
      System::Collections::IEnumerator* myEnumerator =
         myArr->GetEnumerator();

      Array *localArray;
      myArr->Copy(myArr, localArray, myArr->Length);
   }
};
```

В новом синтаксисе объявление объекта ссылочного класса типа с помощью нового декларативного маркера (`^`) называют формально *дескриптора отслеживания* и неформально как *hat*. (Прилагательное отслеживания означает, что ссылочный тип находится в куче среды CLR и можно таким образом легко изменяет расположение при сжатии кучи сборки мусора. Дескриптор отслеживания прозрачно обновляется во время выполнения. Два похожих понятия: *отслеживаемая ссылка* (`%`) и *внутренний указатель* (`interior_ptr<>`), которая обсуждается [семантика типа значения](../dotnet/value-type-semantics.md).

Ниже приведены основные причины удаления декларативного синтаксиса при повторном использовании синтаксиса указателя ISO-C++.

- Использование синтаксиса указателя не позволяет перегружать операторы, которые непосредственно обращаются к ссылочный объект. Вместо этого приходится вызывать оператора с помощью внутреннего имени, например `rV1->op_Addition(rV2)` вместо более интуитивно понятный `rV1+rV2`.

- Число операций указателя, например приведение и арифметика указателя, не разрешено для объектов, хранящихся сборщика мусора куче. Понятие дескриптора отслеживания лучше охватывает природу ссылочного типа среды CLR.

`__gc` Модификатор на дескриптор отслеживания является необязательным и не поддерживается. Использование самого объекта не изменяется. он по-прежнему имеет доступ к членам через оператора выбора членов указателя (`->`). Например вот в предыдущем образце кода управляемых расширений, преобразуются в новый синтаксис:

```
public ref class Form1: public System::Windows::Forms::Form {
private:
   System::ComponentModel::Container^ components;
   Button^ button1;
   DataGrid^ myDataGrid;
   DataSet^ myDataSet;

   void PrintValues( Array^ myArr ) {
      System::Collections::IEnumerator^ myEnumerator =
         myArr->GetEnumerator();

      Array ^localArray;
      myArr->Copy(myArr, localArray, myArr->Length);   }
};
```

## <a name="dynamic-allocation-of-an-object-on-the-clr-heap"></a>Динамическое выделение объекта в куче среды CLR

В управляемых расширениях наличие двух `new` был почти незаметно выражения для размещения между собственной и управляемой кучей. Почти все экземпляры компилятор способен использовать контекст, чтобы определить необходимость выделения памяти из кучи машинный или управляемый. Например, примененная к объекту директива

```
Button *button1 = new Button; // OK: managed heap
int *pi1 = new int;           // OK: native heap
Int32 *pi2 = new Int32;       // OK: managed heap
```

Если не требуется контекстные кучу, можно направить компилятор с помощью `__gc` или `__nogc` ключевое слово. В новом синтаксисе природа двух новых выражений сделано явным, с появлением `gcnew` ключевое слово. Например предыдущие три объявления выглядеть следующим образом в новом синтаксисе:

```
Button^ button1 = gcnew Button;        // OK: managed heap
int * pi1 = new int;                   // OK: native heap
Int32^ pi2 = gcnew Int32; // OK: managed heap
```

Вот инициализации управляемых расширений `Form1` члены, объявленные в предыдущем разделе:

```
void InitializeComponent() {
   components = new System::ComponentModel::Container();
   button1 = new System::Windows::Forms::Button();
   myDataGrid = new DataGrid();

   button1->Click +=
      new System::EventHandler(this, &Form1::button1_Click);
}
```

Ниже приведен тот же приведена к нового синтаксиса. Обратите внимание, что hat не является обязательным для ссылочного типа, если он является целевым объектом `gcnew` выражение.

```
void InitializeComponent() {
   components = gcnew System::ComponentModel::Container;
   button1 = gcnew System::Windows::Forms::Button;
   myDataGrid = gcnew DataGrid;

   button1->Click +=
      gcnew System::EventHandler( this, &Form1::button1_Click );
}
```

## <a name="a-tracking-reference-to-no-object"></a>Отслеживаемая ссылка на объект

В новом синтаксисе `0` больше не представляет нулевым адресом, но обрабатывается как целое число, так же, как `1`, `10`, или `100`. Новый специальный маркер представляет значение null для отслеживаемой ссылки. Например в управляемых расширениях инициализировать ссылочный тип, для решения ни один из объектов следующим образом:

```
// OK: we set obj to refer to no object
Object * obj = 0;

// Error: no implicit boxing
Object * obj2 = 1;
```

В новом синтаксисе, инициализации или присвоения значения тип `Object` приводит к неявной упаковки-преобразования этого типа значения. В новом синтаксисе оба `obj` и `obj2` инициализируются в упакованных объектов Int32, сохраняя значения 0 и 1, соответственно. Пример:

```
// causes the implicit boxing of both 0 and 1
Object ^ obj = 0;
Object ^ obj2 = 1;
```

Таким образом, чтобы выполнить явную инициализацию, назначение и сравнение дескриптора отслеживания значение null, используйте новое ключевое слово, `nullptr`.  Исправленная версия предыдущего примера выглядит следующим образом:

```
// OK: we set obj to refer to no object
Object ^ obj = nullptr;

// OK: we initialize obj2 to a Int32^
Object ^ obj2 = 1;
```

Это усложняет отчасти переносе существующего кода в новый синтаксис. Например рассмотрим следующее объявление класса значение:

```
__value struct Holder {
   Holder( Continuation* c, Sexpr* v ) {
      cont = c;
      value = v;
      args = 0;
      env = 0;
   }

private:
   Continuation* cont;
   Sexpr * value;
   Environment* env;
   Sexpr * args __gc [];
};
```

Здесь оба `args` и `env` являются ссылочными типами среды CLR. Инициализация двух членов в `0` в конструкторе изменяется при переходе на новый синтаксис. Вместо этого их необходимо изменить, чтобы `nullptr`:

```
value struct Holder {
   Holder( Continuation^ c, Sexpr^ v )
   {
      cont = c;
      value = v;
      args = nullptr;
      env = nullptr;
   }

private:
   Continuation^ cont;
   Sexpr^ value;
   Environment^ env;
   array<Sexpr^>^ args;
};
```

Аналогичным образом, проверяет, членов и сравнение их `0` также необходимо изменить для сравнения элементов `nullptr`. Ниже приведен синтаксис управляемых расширений.

```
Sexpr * Loop (Sexpr* input) {
   value = 0;
   Holder holder = Interpret(this, input, env);

   while (holder.cont != 0) {
      if (holder.env != 0) {
         holder=Interpret(holder.cont,holder.value,holder.env);
      }
      else if (holder.args != 0) {
         holder =
         holder.value->closure()->
         apply(holder.cont,holder.args);
      }
   }

   return value;
}
```

Вот новая версия каждого `0` с экземпляром `nullptr`. Средство преобразования позволяет преобразовать путем автоматизации многие, если не все совпадения, включая использование `NULL` макрос.

```
Sexpr ^ Loop (Sexpr^ input) {
   value = nullptr;
   Holder holder = Interpret(this, input, env);

   while ( holder.cont != nullptr ) {
      if ( holder.env != nullptr ) {
         holder=Interpret(holder.cont,holder.value,holder.env);
      }
      else if (holder.args != nullptr ) {
         holder =
         holder.value->closure()->
         apply(holder.cont,holder.args);
      }
   }

   return value;
}
```

`nullptr` Преобразуется в любой указатель или тип дескриптора отслеживания, но не повышается в целочисленный тип. Например, в следующем наборе инициализаций `nullptr` допустим только как начальное значение для первых двух.

```
// OK: we set obj and pstr to refer to no object
Object^ obj = nullptr;
char*   pstr = nullptr; // 0 would also work here

// Error: no conversion of nullptr to 0
int ival = nullptr;
```

Аналогично Если перегруженный набор методов, таких как следующие:

```
void f( Object^ ); // (1)
void f( char* );   // (2)
void f( int );     // (3)
```

Вызов с `nullptr` литерал, как указано ниже,

```
// Error: ambiguous: matches (1) and (2)
f(  nullptr );
```

неоднозначен, так как `nullptr` соответствующий дескриптор отслеживания и указатель и нет предпочтение ни одного типа по отношению к другому. (Эта ситуация требует явного приведения для устранения неоднозначности.)

Вызов с `0` точно совпадает с экземпляром (3):

```
// OK: matches (3)
f( 0 );
```

так как `0` имеет целочисленный тип. Были `f(int)` отсутствует, вызов будет однозначно соответствовать `f(char*)` через стандартное преобразование. Правила сопоставления дать приоритет точного совпадения над стандартным преобразованием. При отсутствии точного соответствия стандартное преобразование получает приоритет над неявной упаковки-преобразования типа значения. Вот почему отсутствует неоднозначность.

## <a name="see-also"></a>См. также

[Управляемые типы (C + +/ CL)](../dotnet/managed-types-cpp-cl.md)<br/>
[Классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md)<br/>
[Оператор дескриптора объекта (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)<br/>
[nullptr](../windows/nullptr-cpp-component-extensions.md)