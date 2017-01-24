---
title: "Обзор изменений (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: c0bbbd6b-c5c4-44cf-a6ca-c1010c377e9d
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Обзор изменений (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В данном обзоре приводятся примеры некоторых изменений в языке от управляемых расширений C\+\+ до [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  Дополнительные сведения можно получить, перейдя по ссылке, приведенной после каждого примера.  
  
## Отсутствие ключевых слов с двойным символом подчеркивания  
 Двойной символ подчеркивания перед всеми ключевыми словами больше не используется за одним исключением.  Таким образом, вместо ключевого слова `__value` используется `value`, вместо `__interface` — `interface` и т. д.  Во избежание конфликтов имен ключевых слов и идентификаторов ключевые слова используются в первую очередь как контекстуальные.  
  
 Дополнительные сведения см. в разделе [Ключевые слова языка \(C\+\+\/CLI\)](../Topic/Language%20Keywords%20\(C++-CLI\).md).  
  
## Объявления классов  
 Синтаксис управляемых расширений:  
  
```  
__gc class Block {};                           // reference class  
__value class Vector {};                       // value class  
__interface I {};                        // interface class  
__gc __abstract class Shape {};                // abstract class  
__gc __sealed class Shape2D : public Shape {}; // derived class  
```  
  
 Новый синтаксис:  
  
```  
ref class Block {};                // reference class  
value class Vector {};             // value class  
interface class I {};        // interface class  
ref class Shape abstract {};       // abstract class  
ref class Shape2D sealed: Shape{}; // derived class  
```  
  
 Дополнительные сведения см. в разделе [Управляемые типы \(C\+\+\/CL\)](../dotnet/managed-types-cpp-cl.md).  
  
## Объявление объектов  
 Синтаксис управляемых расширений:  
  
```  
public __gc class Form1 : public System::Windows::Forms::Form {  
private:  
   System::ComponentModel::Container __gc *components;  
   System::Windows::Forms::Button   __gc *button1;  
   System::Windows::Forms::DataGrid __gc *myDataGrid;     
   System::Data::DataSet  __gc *myDataSet;  
};  
```  
  
 Новый синтаксис:  
  
```  
public ref class Form1 : System::Windows::Forms::Form {  
   System::ComponentModel::Container^ components;  
   System::Windows::Forms::Button^ button1;  
   System::Windows::Forms::DataGrid^ myDataGrid;  
   System::Data::DataSet^ myDataSet;  
};  
```  
  
 Дополнительные сведения см. в разделе [Объявление объекта ссылочного класса в среде CLR](../dotnet/declaration-of-a-clr-reference-class-object.md).  
  
### Выделение управляемой кучи  
 Синтаксис управляемых расширений:  
  
```  
Button* button1 = new Button; // managed heap  
int *pi1 = new int;           // native heap  
Int32 *pi2 = new Int32;       // managed heap  
```  
  
 Новый синтаксис:  
  
```  
Button^ button1 = gcnew Button;        // managed heap  
int * pi1 = new int;                   // native heap  
Int32^ pi2 = gcnew Int32;              // managed heap  
```  
  
 Дополнительные сведения см. в разделе [Объявление объекта ссылочного класса в среде CLR](../dotnet/declaration-of-a-clr-reference-class-object.md).  
  
### Ссылка с отслеживанием на несуществующий объект  
 Синтаксис управляемых расширений:  
  
```  
// OK: we set obj to refer to no object  
Object * obj = 0;  
  
// Error: no implicit boxing  
Object * obj2 = 1;  
```  
  
 Новый синтаксис:  
  
```  
// Incorrect Translation  
// causes the implicit boxing of both 0 and 1  
Object ^ obj = 0;  
Object ^ obj2 = 1;  
  
// Correct Translation  
// OK: we set obj to refer to no object  
Object ^ obj = nullptr;  
  
// OK: we initialize obj2 to an Int32^  
Object ^ obj2 = 1;  
```  
  
 Дополнительные сведения см. в разделе [Объявление объекта ссылочного класса в среде CLR](../dotnet/declaration-of-a-clr-reference-class-object.md).  
  
## Объявление массива  
 Структура массива CLR была изменена.  Он подобен коллекции шаблонов `vector`, но сопоставлен с базовым классом `System::Array`, т. е. не является реализацией шаблона.  
  
 Дополнительные сведения см. в разделе [Объявление массива CLR](../dotnet/declaration-of-a-clr-array.md).  
  
### Массив в качестве параметра  
 Синтаксис массива управляемых расширений:  
  
```  
void PrintValues( Object* myArr __gc[]);   
void PrintValues( int myArr __gc[,,]);   
```  
  
 Новый синтаксис массива:  
  
```  
void PrintValues( array<Object^>^ myArr );  
void PrintValues( array<int,3>^ myArr );  
```  
  
### Массив в качестве возвращаемого типа  
 Синтаксис массива управляемых расширений:  
  
```  
Int32 f() [];   
int GetArray() __gc[];  
```  
  
 Новый синтаксис массива:  
  
```  
array<Int32>^ f();  
array<int>^ GetArray();  
```  
  
### Быстрая инициализация локального массива CLR  
 Синтаксис массива управляемых расширений:  
  
```  
int GetArray() __gc[] {  
   int a1 __gc[] = { 1, 2, 3, 4, 5 };  
   Object* myObjArray __gc[] = { __box(26), __box(27), __box(28),  
                                 __box(29), __box(30) };  
  
   return a1;  
}  
```  
  
 Новый синтаксис массива:  
  
```  
array<int>^ GetArray() {  
   array<int>^ a1 = {1,2,3,4,5};  
   array<Object^>^ myObjArray = {26,27,28,29,30};  
  
   return a1;  
}  
```  
  
### Явное объявление массива CLR  
 Синтаксис массива управляемых расширений:  
  
```  
Object* myArray[] = new Object*[2];  
String* myMat[,] = new String*[4,4];  
```  
  
 Новый синтаксис массива:  
  
```  
array<Object^>^ myArray = gcnew array<Object^>(2);  
array<String^,2>^ myMat = gcnew array<String^,2>(4,4);  
```  
  
 Новое в языке: явная инициализация массива после вызова gcnew:  
  
```  
// explicit initialization list follow gcnew   
// is not supported in Managed Extensions  
array<Object^>^ myArray =   
   gcnew array<Object^>(4){ 1, 1, 2, 3 };  
```  
  
## Скалярные свойства  
 Синтаксис свойства управляемых расширений:  
  
```  
public __gc __sealed class Vector {  
   double _x;  
  
public:  
   __property double get_x(){ return _x; }  
   __property void set_x( double newx ){ _x = newx; }  
};  
```  
  
 Новый синтаксис свойства:  
  
```  
public ref class Vector sealed {   
   double _x;  
  
public:  
   property double x   
   {  
      double get()             { return _x; }  
      void   set( double newx ){ _x = newx; }  
   } // Note: no semi-colon …  
};  
```  
  
 Новое в языке: тривиальные свойства:  
  
```  
public ref class Vector sealed {   
public:  
   // equivalent shorthand property syntax  
   // backing store is not accessible  
   property double x;   
};  
```  
  
 Дополнительные сведения см. в разделе [Объявление свойства](../dotnet/property-declaration.md).  
  
## Индексированные свойства  
 Синтаксис индексированного свойства управляемых расширений:  
  
```  
public __gc class Matrix {  
   float mat[,];  
  
public:   
   __property void set_Item( int r, int c, float value) { mat[r,c] = value; }  
   __property int get_Item( int r, int c ) { return mat[r,c]; }  
};  
```  
  
 Новый синтаксис индексированного свойства:  
  
```  
public ref class Matrix {  
   array<float, 2>^ mat;  
  
public:  
   property float Item [int,int] {  
      float get( int r, int c ) { return mat[r,c]; }  
      void set( int r, int c, float value ) { mat[r,c] = value; }  
   }  
};  
```  
  
 Новое в языке: индексированные свойства на уровне класса:  
  
```  
public ref class Matrix {  
   array<float, 2>^ mat;  
  
public:  
   // ok: class level indexer now  
   //     Matrix mat;  
   //     mat[ 0, 0 ] = 1;   
   //  
   // invokes the set accessor of the default indexer  
  
   property float default [int,int] {  
      float get( int r, int c ) { return mat[r,c]; }  
      void set( int r, int c, float value ) { mat[r,c] = value; }  
   }  
};  
```  
  
 Дополнительные сведения см. в разделе [Объявление индекса свойства](../dotnet/property-index-declaration.md).  
  
## Перегруженные операторы  
 Синтаксис перегрузки оператора управляемых расширений:  
  
```  
public __gc __sealed class Vector {  
public:  
   Vector( double x, double y, double z );  
  
   static bool    op_Equality( const Vector*, const Vector* );  
   static Vector* op_Division( const Vector*, double );  
};  
  
int main() {  
   Vector *pa = new Vector( 0.231, 2.4745, 0.023 );  
   Vector *pb = new Vector( 1.475, 4.8916, -1.23 );   
  
   Vector *pc = Vector::op_Division( pa, 4.8916 );  
  
   if ( Vector::op_Equality( pa, pc ))  
      ;  
}  
```  
  
 Новый синтаксис перегрузки оператора:  
  
```  
public ref class Vector sealed {  
public:  
   Vector( double x, double y, double z );  
  
   static bool    operator ==( const Vector^, const Vector^ );  
   static Vector^ operator /( const Vector^, double );  
};  
  
int main() {  
   Vector^ pa = gcnew Vector( 0.231, 2.4745, 0.023 );  
   Vector^ pb = gcnew Vector( 1.475, 4.8916, -1.23 );  
  
   Vector^ pc = pa / 4.8916;  
   if ( pc == pa )  
      ;  
}  
```  
  
 Дополнительные сведения см. в разделе [Перегруженные операторы](../dotnet/overloaded-operators.md).  
  
## Операторы преобразования  
 Синтаксис оператора преобразования управляемых расширений:  
  
```  
__gc struct MyDouble {  
   static MyDouble* op_Implicit( int i );   
   static int op_Explicit( MyDouble* val );  
   static String* op_Explicit( MyDouble* val );   
};  
```  
  
 Новый синтаксис оператора преобразования:  
  
```  
ref struct MyDouble {  
public:  
   static operator MyDouble^ ( int i );  
   static explicit operator int ( MyDouble^ val );  
   static explicit operator String^ ( MyDouble^ val );  
};  
```  
  
 Дополнительные сведения см. в разделе [Изменение операторов преобразования](../dotnet/changes-to-conversion-operators.md).  
  
## Явное переопределение элемента интерфейса  
 Синтаксис явного переопределения управляемых расширений:  
  
```  
public __gc class R : public ICloneable {  
   // to be used through ICloneable  
   Object* ICloneable::Clone();  
  
   // to be used through an R  
   R* Clone();  
};  
```  
  
 Новый синтаксис явного переопределения:  
  
```  
public ref class R : public ICloneable {  
   // to be used through ICloneable  
   virtual Object^ InterfaceClone() = ICloneable::Clone;  
  
   // to be used through an R   
   virtual R^ Clone();  
};  
```  
  
 Дополнительные сведения см. в разделе [Явное переопределение элемента интерфейса](../dotnet/explicit-override-of-an-interface-member.md).  
  
## Закрытые виртуальные функции  
 Синтаксис закрытой виртуальной функции управляемых расширений:  
  
```  
__gc class Base {  
private:  
   // inaccessible to a derived class  
   virtual void g();   
};  
  
__gc class Derived : public Base {  
public:  
   // ok: g() overrides Base::g()  
   virtual void g();  
};  
```  
  
 Новый синтаксис закрытой виртуальной функции:  
  
```  
ref class Base {  
private:  
   // inaccessible to a derived class  
   virtual void g();   
};  
  
ref class Derived : public Base {  
public:  
   // error: cannot override: Base::g() is inaccessible  
   virtual void g() override;  
};  
```  
  
 Дополнительные сведения см. в разделе [Закрытые виртуальные функции](../Topic/Private%20Virtual%20Functions.md).  
  
## Тип перечисления Enum в среде CLR  
 Синтаксис перечисления управляемых расширений:  
  
```  
__value enum e1 { fail, pass };  
public __value enum e2 : unsigned short  {   
   not_ok = 1024,   
   maybe, ok = 2048   
};    
```  
  
 Новый синтаксис перечисления:  
  
```  
enum class e1 { fail, pass };  
public enum class e2 : unsigned short {   
   not_ok = 1024,  
   maybe, ok = 2048   
};  
```  
  
 Кроме этого незначительного изменения синтаксиса изменилось и поведение типа перечисления Enum в CLR:  
  
-   Больше не поддерживается предварительное объявление типа перечисления Enum.  
  
-   Разрешение перегрузки между встроенными арифметическими типами и иерархией классов объектов в управляемых расширениях и [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] изменилось на обратное.  В качестве побочного эффекта типы перечисления CLR не могут больше неявно преобразовываться в арифметические типы.  
  
-   В новом синтаксисе перечисление CLR имеет собственную область действия, чего не было в управляемых расширениях.  Ранее перечислители были видны внутри области действия перечисления, теперь же перечислители инкапсулированы в области действия перечисления.  
  
 Дополнительные сведения см. в разделе [Тип перечисления Enum в среде CLR](../dotnet/clr-enum-type.md).  
  
## Ключевое слово "\_\_box" устранено  
 Синтаксис упаковки\-преобразования управляемых расширений:  
  
```  
Object *o = __box( 1024 ); // explicit boxing  
```  
  
 Новый синтаксис упаковки\-преобразования:  
  
```  
Object ^o = 1024; // implicit boxing  
```  
  
 Дополнительные сведения см. в разделе [Дескриптор отслеживания для упакованных значений](../dotnet/a-tracking-handle-to-a-boxed-value.md).  
  
## Закрепляющий указатель  
 Синтаксис закрепляющего указателя управляемых расширений:  
  
```  
__gc struct H { int j; };  
  
int main() {  
   H * h = new H;  
   int __pin * k = & h -> j;  
};  
```  
  
 Новый синтаксис закрепляющего указателя:  
  
```  
ref struct H { int j; };  
  
int main() {  
   H^ h = gcnew H;  
   pin_ptr<int> k = &h->j;  
}  
```  
  
 Дополнительные сведения см. в разделе [Семантика типа значения](../Topic/Value%20Type%20Semantics.md).  
  
## Замена ключевого слова "\_\_typeof" на "typeid"  
 Синтаксис ключевого слова "typeof" управляемых расширений:  
  
```  
Array* myIntArray =   
   Array::CreateInstance( __typeof(Int32), 5 );  
```  
  
 Новый синтаксис ключевого слова "typeid":  
  
```  
Array^ myIntArray =   
   Array::CreateInstance( Int32::typeid, 5 );  
```  
  
 Дополнительные сведения см. в разделе [Переход typeof в T::typeid](../dotnet/typeof-goes-to-t-typeid.md).  
  
## См. также  
 [Основы миграции C\+\+\/CLI](../dotnet/cpp-cli-migration-primer.md)   
 [\(NOTINBUILD\)Managed Extensions for C\+\+ Syntax Upgrade Checklist](http://msdn.microsoft.com/ru-ru/edbded88-7ef3-4757-bd9d-b8f48ac2aada)   
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)