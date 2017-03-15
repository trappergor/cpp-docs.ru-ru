---
title: "Объявление объекта ссылочного класса в среде CLR | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ссылочные типы, среда CLR"
  - "типы [C++], ссылочные типы"
ms.assetid: 6d64f746-3715-4948-ada3-88859f4150e4
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Объявление объекта ссылочного класса в среде CLR
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Синтаксис объявления и реализации объекта ссылочного типа класса изменился в [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] по сравнению с управляемыми расширениями для C\+\+.  
  
 В управляемых расширениях объект ссылочного типа класса объявляется с помощью синтаксиса указателя ISO\-C\+\+ и необязательного использования ключевого слова `__gc`, которое находится с левой стороны звезды \(`*`\).  Например, ниже представлено несколько объявлений объектов ссылочных типов класса в синтаксисе управляемого расширения:  
  
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
  
 В новом синтаксисе объект ссылочного типа класса объявляется с помощью нового декларативного маркера \(`^`\), который формально называется *дескриптором отслеживания*, а неформально как *шапка* \(прилагательное "отслеживания" означает, что ссылочный тип находится в куче среды CLR и, следовательно, легко изменяет расположение при сжатии кучи сборщиком мусора\).  Дескриптор отслеживания прозрачно обновляется во время выполнения.  Два похожих понятия: *ссылочное отслеживание* \(`%`\) и *внутренний указатель* \(`interior_ptr<>`\) рассматриваются в разделе [Семантика типа значения](../Topic/Value%20Type%20Semantics.md).  
  
 Ниже приведены основные причины удаления декларативного синтаксиса при повторном использовании синтаксиса указателя ISO\-C\+\+:  
  
-   Использование синтаксиса указателя не позволяет перегружать операторы, которые непосредственно обращаются к ссылочному объекту.  Приходится вызывать оператор с помощью внутреннего имени, такого как `rV1->op_Addition(rV2)`, а не с помощью более интуитивного `rV1+rV2`.  
  
-   Определенное количество операций указателя, например приведение и арифметика указателя, не размещаются в сохраненных объектах кучи сборщика мусора.  Представление дескриптора отслеживания лучше охватывает природу ссылочного типа среды CLR.  
  
 Модификатор `__gc` в дескрипторе отслеживания является необязательным и, следовательно, не поддерживается.  Метод использования объекта не изменяется. Объект имеет доступ к членам с помощью оператора в выборке членов указателя \(`->`\).  Например, ниже приведен пример кода предыдущих управляемых расширений, транслированных в новом синтаксисе:  
  
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
  
## Динамическое размещение объекта в куче среды CLR  
 В управляемых расширениях наличие двух выражений `new` для размещения между собственной и управляемой кучей было в общем и целом прозрачно.  В большей части случаев компилятор, используя контекст, может определить размещать ли память из собственной или управляемой кучи.  Например:  
  
```  
Button *button1 = new Button; // OK: managed heap  
int *pi1 = new int;           // OK: native heap  
Int32 *pi2 = new Int32;       // OK: managed heap  
```  
  
 Если не требуется размещать контекстно\-зависимую кучу, можно направить компилятор с помощью ключевого слова `__gc` или `__nogc`.  В новом синтаксисе различная природа двух новых выражений указана явно; этого удалось достичь введением ключевого слова `gcnew`.  Например, предыдущие три объявления имеют в новом синтаксисе следующий вид:  
  
```  
Button^ button1 = gcnew Button;        // OK: managed heap  
int * pi1 = new int;                   // OK: native heap  
Int32^ pi2 = gcnew Int32; // OK: managed heap  
```  
  
 Ниже представлена инициализация управляемыми расширениями членов `Form1`, объявленных в предыдущем примере:  
  
```  
void InitializeComponent() {  
   components = new System::ComponentModel::Container();  
   button1 = new System::Windows::Forms::Button();  
   myDataGrid = new DataGrid();  
  
   button1->Click +=   
      new System::EventHandler(this, &Form1::button1_Click);  
}  
```  
  
 Ниже приведен тот же самый пример, но уже в новом синтаксисе.  Обратите внимание, что "шляпа" не требуется для ссылочных типов, если они являются целью выражения `gcnew`.  
  
```  
void InitializeComponent() {  
   components = gcnew System::ComponentModel::Container;  
   button1 = gcnew System::Windows::Forms::Button;  
   myDataGrid = gcnew DataGrid;  
  
   button1->Click +=   
      gcnew System::EventHandler( this, &Form1::button1_Click );  
}  
```  
  
## Ссылка с отслеживанием на несуществующий объект  
 В новом синтаксисе объект `0` не представляет более адрес "null", но обрабатывается как целое число, так же как `1`, `10` или `100`.  Новый особый маркер представляет значение NULL для ссылки с отслеживанием.  Например, в управляемых расширениях ссылочный тип с адресом на несуществующий объект инициализируется следующим образом:  
  
```  
// OK: we set obj to refer to no object  
Object * obj = 0;  
  
// Error: no implicit boxing  
Object * obj2 = 1;  
```  
  
 В новом синтаксисе инициализация или назначения типа значения в `Object` вызывает неявную упаковку\-преобразование типа значения.  В новом синтаксисе значения `obj` и `obj2` инициализируются в упакованных объектах с адресом Int32, соответственно сохраняя значения 0 и 1.  Примеры.  
  
```  
// causes the implicit boxing of both 0 and 1  
Object ^ obj = 0;  
Object ^ obj2 = 1;  
```  
  
 Таким образом, чтобы выполнить явную инициализацию, назначение и сравнение дескриптора отслеживания со значением NULL, используйте новое ключевое слово `nullptr`.  Исправленная версия предыдущего примера, выполняющаяся без ошибок, представлена ниже:  
  
```  
// OK: we set obj to refer to no object  
Object ^ obj = nullptr;  
  
// OK: we initialize obj2 to a Int32^  
Object ^ obj2 = 1;  
```  
  
 Тем не менее, это вызывает некоторые трудности при переносе существующего кода в новый синтаксис.  Например, рассмотрим объявление класса значений:  
  
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
  
 Представлены ссылочные типы `args` и `env` в среде CLR.  Инициализация двух членов в `0` в конструкторе изменяется при трансляции в новый синтаксис.  Члены следует преобразовать в `nullptr`:  
  
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
  
 Аналогичным образом, данные тестирования членов и сравнение их с `0` также необходимо изменить, чтобы иметь возможность сравнить члены с `nullptr`.  Ниже представлен синтаксис управляемых расширений:  
  
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
  
 Ниже представлена новая версия с изменением с `0` на `nullptr`.  Автоматизация позволяет программе трансляции преобразовать многие, если не все совпадения, в том числе и использование макроса `NULL`.  
  
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
  
 `nullptr` преобразуется в указатель или тип дескриптора отслеживания, но не повышается до типа интеграла.  Например, в следующем наборе инициализаций `nullptr` является действительным только в том случае, если начальное значение относится к первым двум.  
  
```  
// OK: we set obj and pstr to refer to no object  
Object^ obj = nullptr;  
char*   pstr = nullptr; // 0 would also work here  
  
// Error: no conversion of nullptr to 0 …  
int ival = nullptr;  
```  
  
 Аналогично в следующем примере представлен перегруженный набор методов:  
  
```  
void f( Object^ ); // (1)  
void f( char* );   // (2)  
void f( int );     // (3)  
```  
  
 В следующем примере показан вызов `nullptr` с литералом,  
  
```  
// Error: ambiguous: matches (1) and (2)  
f(  nullptr );  
```  
  
 который является неоднозначным, поскольку значение `nullptr` совпадает для дескриптора отслеживания и указателя, и при этом предпочтение не отдается ни одному из указанных типов \(эта ситуация требует явного приведение для устранения неоднозначности\).  
  
 Вызов с `0` точно совпадает с экземпляром \(3\):  
  
```  
// OK: matches (3)  
f( 0 );  
```  
  
 поскольку `0` является типом с целым числом.  Если бы `f(int)` не был представлен, вызов бы однозначно совпал бы со стандартным преобразованием `f(char*)`.  Правила совпадения оставляют приоритет за точным совпадением над стандартным преобразованием.  При отсутствии точного совпадения стандартное преобразование получает приоритет над неявной упаковкой\-преобразованием типа значения.  Это объясняет отсутствие неоднозначности.  
  
## См. также  
 [Управляемые типы \(C\+\+\/CL\)](../dotnet/managed-types-cpp-cl.md)   
 [Классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md)   
 [Оператор дескриптора объекта \(^\)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)   
 [nullptr](../windows/nullptr-cpp-component-extensions.md)