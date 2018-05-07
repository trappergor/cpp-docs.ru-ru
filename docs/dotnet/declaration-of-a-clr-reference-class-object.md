---
title: Объявление объекта ссылочного класса CLR | Документы Microsoft
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
ms.openlocfilehash: 12cead3a142c69da56390ca6f5bf32cecc3b0075
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="declaration-of-a-clr-reference-class-object"></a>Объявление объекта ссылочного класса в среде CLR
Синтаксис для объявления и создания экземпляра объекта ссылочного типа класса был изменен с управляемых расширений для C++ к Visual C++.  
  
 В управляемых расширениях объекта ссылочного типа класса объявляется с помощью синтаксиса указателя ISO C++, с необязательным использованием `__gc` ключевое слово слева звезды (`*`). Например ниже приведены различные ссылки объявлений объектов типа класса в синтаксисе управляемых расширений.  
  
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
  
 В новом синтаксисе объекта ссылочного типа класса объявляется с помощью нового декларативного маркера (`^`) называют формально *дескриптора отслеживания* и более неофициально как *hat*. (Прилагательное отслеживания означает, что ссылочный тип находится в куче среды CLR и может поэтому легко изменяет расположение при сжатии кучи сборки мусора. Дескриптор отслеживания прозрачно обновляется во время выполнения. Два похожих понятия: *отслеживаемая ссылка* (`%`) и *внутренний указатель* (`interior_ptr<>`), о которой рассказывается в [семантика типа значения](../dotnet/value-type-semantics.md).  
  
 Ниже приведены основные причины удаления декларативного синтаксиса при повторном использовании синтаксиса указателя ISO C++.  
  
-   Использование синтаксиса указателя не позволяет перегружать операторы, которые непосредственно обращаются к ссылочного объекта. Вместо этого приходится вызывать оператор с помощью внутреннего имени, например `rV1->op_Addition(rV2)` вместо более интуитивный `rV1+rV2`.  
  
-   Количество операций указателя, например приведение и арифметика указателя, не разрешено для объектов, хранящихся на сборщика мусора куче. Понятие дескриптора отслеживания лучше охватывает природу ссылочного типа среды CLR.  
  
 `__gc` Модификатор в дескрипторе отслеживания является необязательным и не поддерживается. Использование самого объекта не изменяется. он по-прежнему имеет доступ к членам через оператора выбора указателя на член (`->`). Например ниже приведен предыдущий пример кода управляемых расширений, реализованного с использованием нового синтаксиса:  
  
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
 В управляемых расширениях наличие двух `new` выражения для размещения между собственной и управляемой кучей было во многом прозрачно. Почти все экземпляры компилятор способен использовать контекст, чтобы определить необходимость выделить память из кучи машинного или управляемого. Например, примененная к объекту директива  
  
```  
Button *button1 = new Button; // OK: managed heap  
int *pi1 = new int;           // OK: native heap  
Int32 *pi2 = new Int32;       // OK: managed heap  
```  
  
 Если не требуется контекстно-зависимое кучу, можно направить компилятор с помощью `__gc` или `__nogc` ключевое слово. В новом синтаксисе природа двух новых выражений преобразуются в явные с появлением `gcnew` ключевое слово. Например предыдущие три объявления выглядеть следующим образом в новом синтаксисе:  
  
```  
Button^ button1 = gcnew Button;        // OK: managed heap  
int * pi1 = new int;                   // OK: native heap  
Int32^ pi2 = gcnew Int32; // OK: managed heap  
```  
  
 Ниже приведен инициализация управляемыми расширениями `Form1` члены, объявленные в предыдущем разделе:  
  
```  
void InitializeComponent() {  
   components = new System::ComponentModel::Container();  
   button1 = new System::Windows::Forms::Button();  
   myDataGrid = new DataGrid();  
  
   button1->Click +=   
      new System::EventHandler(this, &Form1::button1_Click);  
}  
```  
  
 Ниже приведен тот же приведена к нового синтаксиса. Обратите внимание, что крышки не является обязательным для ссылочного типа, если он является целевым объектом `gcnew` выражение.  
  
```  
void InitializeComponent() {  
   components = gcnew System::ComponentModel::Container;  
   button1 = gcnew System::Windows::Forms::Button;  
   myDataGrid = gcnew DataGrid;  
  
   button1->Click +=   
      gcnew System::EventHandler( this, &Form1::button1_Click );  
}  
```  
  
## <a name="a-tracking-reference-to-no-object"></a>Отслеживаемая ссылка на несуществующий объект  
 В новом синтаксисе `0` больше не представляет значение null, адрес, но обрабатывается как целое число, так же, как `1`, `10`, или `100`. Новый особый маркер представляет значение null для отслеживаемой ссылки. Например в управляемых расширениях инициализировать ссылочного типа адресом на несуществующий объект следующим образом:  
  
```  
// OK: we set obj to refer to no object  
Object * obj = 0;  
  
// Error: no implicit boxing  
Object * obj2 = 1;  
```  
  
 В новом синтаксисе инициализации или присвоения значения типа к `Object` вызывает неявная упаковка-преобразование типа значения. В новом синтаксисе оба `obj` и `obj2` инициализируются в упакованных объектов Int32, сохраняя значения 0 и 1, соответственно. Пример:  
  
```  
// causes the implicit boxing of both 0 and 1  
Object ^ obj = 0;  
Object ^ obj2 = 1;  
```  
  
 Таким образом, чтобы выполнить явную инициализацию, назначение и сравнение дескриптора отслеживания со значением null, используйте новое ключевое слово `nullptr`.  Исправленная версия предыдущего примера выглядит следующим образом:  
  
```  
// OK: we set obj to refer to no object  
Object ^ obj = nullptr;  
  
// OK: we initialize obj2 to a Int32^  
Object ^ obj2 = 1;  
```  
  
 Это осложняет немного перенос существующего кода в новый синтаксис. Например рассмотрим следующее объявление класса значение:  
  
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
  
 Здесь оба `args` и `env` являются ссылочными типами среды CLR. Инициализация двух членов в `0` в конструкторе изменяется при трансляции в новый синтаксис. Вместо этого их необходимо изменить, чтобы `nullptr`:  
  
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
  
 Ниже представлена новая версия, заменив каждый `0` экземпляра с `nullptr`. Средство преобразования позволяет преобразовать автоматизируя многие, если не все совпадения, включая использование `NULL` макрос.  
  
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
  
 `nullptr` Преобразуется в любой указатель или тип дескриптора отслеживания, но не переходят в целочисленный тип. Например, в следующем наборе инициализаций `nullptr` допустим только как начальное значение для первых двух.  
  
```  
// OK: we set obj and pstr to refer to no object  
Object^ obj = nullptr;  
char*   pstr = nullptr; // 0 would also work here  
  
// Error: no conversion of nullptr to 0  
int ival = nullptr;  
```  
  
 Аналогично имеется набор перегруженных методов из следующего:  
  
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
  
 является неоднозначным поскольку `nullptr` соответствует дескриптора отслеживания и указателя и нет предпочтение ни одного типа по отношению к другому. (Эта ситуация требует явного приведения для устранения неоднозначности).  
  
 Вызов с `0` точно совпадает с экземпляром (3):  
  
```  
// OK: matches (3)  
f( 0 );  
```  
  
 Поскольку `0` имеет тип integer. Были `f(int)` отсутствует, вызов будет однозначно соответствовать `f(char*)` через стандартное преобразование. Правила сопоставления повышения приоритета точного совпадения над стандартное преобразование. При отсутствии точного совпадения стандартное преобразование получает приоритет над неявной упаковки-преобразования типа значения. Именно поэтому отсутствие неоднозначности.  
  
## <a name="see-also"></a>См. также  
 [Управляемые типы (C + +/ CL)](../dotnet/managed-types-cpp-cl.md)   
 [Классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md)   
 [Оператор дескриптора объекта (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)   
 [nullptr](../windows/nullptr-cpp-component-extensions.md)