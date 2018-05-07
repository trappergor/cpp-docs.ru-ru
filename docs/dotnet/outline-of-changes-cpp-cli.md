---
title: Обзор изменений (C + +/ CLI) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c0bbbd6b-c5c4-44cf-a6ca-c1010c377e9d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2a9662f73844013a944fc2b04ce6d3627d4e4b80
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="outline-of-changes-ccli"></a>Обзор изменений (C++/CLI)
Данная структура приводятся примеры некоторых изменений в языке от управляемых расширений для C++ к Visual C++. Перейдите по ссылке, приведенной после каждого примера для получения дополнительной информации.  
  
## <a name="no-double-underscore-keywords"></a>Ключевые слова не двойной знак подчеркивания  
 Двойной знак подчеркивания перед всеми ключевыми словами был удален, за одним исключением. Таким образом `__value` становится `value`, и `__interface` становится `interface`, и т. д. Во избежание конфликтов имен ключевых слов и идентификаторов в пользовательском коде, ключевые слова в первую очередь как контекстуальные.  
  
 В разделе [ключевые слова языка (C + +/ CLI)](../dotnet/language-keywords-cpp-cli.md) для получения дополнительной информации.  
  
## <a name="class-declarations"></a>Объявления класса  
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
  
 В разделе [управляемые типы (C + +/ CL)](../dotnet/managed-types-cpp-cl.md) для получения дополнительной информации.  
  
## <a name="object-declaration"></a>Объявление объектов  
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
  
 В разделе [объявление объекта ссылочного класса CLR](../dotnet/declaration-of-a-clr-reference-class-object.md) для получения дополнительной информации.  
  
### <a name="managed-heap-allocation"></a>Выделения памяти в куче  
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
  
 В разделе [объявление объекта ссылочного класса CLR](../dotnet/declaration-of-a-clr-reference-class-object.md) для получения дополнительной информации.  
  
### <a name="a-tracking-reference-to-no-object"></a>Отслеживаемая ссылка на несуществующий объект  
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
  
 В разделе [объявление объекта ссылочного класса CLR](../dotnet/declaration-of-a-clr-reference-class-object.md) для получения дополнительной информации.  
  
## <a name="array-declaration"></a>Объявление массива  
 Массив CLR был изменен. Это похоже на stl `vector` коллекцию шаблонов, но сопоставлен с базовым `System::Array` класса — то есть, это не является реализацией шаблона.  
  
 В разделе [объявление массива CLR](../dotnet/declaration-of-a-clr-array.md) для получения дополнительной информации.  
  
### <a name="array-as-parameter"></a>Массив в качестве параметра  
 Синтаксис управляемых расширений массива:  
  
```  
void PrintValues( Object* myArr __gc[]);   
void PrintValues( int myArr __gc[,,]);   
```  
  
 Новый синтаксис массива:  
  
```  
void PrintValues( array<Object^>^ myArr );  
void PrintValues( array<int,3>^ myArr );  
```  
  
### <a name="array-as-return-type"></a>Массив в качестве типа возвращаемого значения  
 Синтаксис управляемых расширений массива:  
  
```  
Int32 f() [];   
int GetArray() __gc[];  
```  
  
 Новый синтаксис массива:  
  
```  
array<Int32>^ f();  
array<int>^ GetArray();  
```  
  
### <a name="shorthand-initialization-of-local-clr-array"></a>Быстрая инициализация локального массива CLR  
 Синтаксис управляемых расширений массива:  
  
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
  
### <a name="explicit-clr-array-declaration"></a>Явное объявление массива CLR  
 Синтаксис управляемых расширений массива:  
  
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
  
## <a name="scalar-properties"></a>Скалярные свойства  
 Свойство синтаксис управляемых расширений:  
  
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
   } // Note: no semi-colon  
};  
```  
  
 Новое в языке: тривиальные свойства  
  
```  
public ref class Vector sealed {   
public:  
   // equivalent shorthand property syntax  
   // backing store is not accessible  
   property double x;   
};  
```  
  
 В разделе [объявление свойства](../dotnet/property-declaration.md) для получения дополнительной информации.  
  
## <a name="indexed-properties"></a>Индексированные свойства  
 Управляемые расширения синтаксис индексированного свойства:  
  
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
  
 Новое в языке: индексированные свойства на уровне класса  
  
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
  
 В разделе [объявление индекса свойства](../dotnet/property-index-declaration.md) для получения дополнительной информации.  
  
## <a name="overloaded-operators"></a>Перегруженные операторы  
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
  
 В разделе [перегруженные операторы](../dotnet/overloaded-operators.md) для получения дополнительной информации.  
  
## <a name="conversion-operators"></a>Операторы преобразования  
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
  
 В разделе [примет операторы преобразования](../dotnet/changes-to-conversion-operators.md) для получения дополнительной информации.  
  
## <a name="explicit-override-of-an-interface-member"></a>Явное переопределение элемента интерфейса  
 Явного переопределения управляемых расширений синтаксиса:  
  
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
  
 В разделе [явное переопределение элемента интерфейса](../dotnet/explicit-override-of-an-interface-member.md) для получения дополнительной информации.  
  
## <a name="private-virtual-functions"></a>Закрытые виртуальные функции  
 Синтаксис управляемых расширений закрытой виртуальной функции:  
  
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
  
 Новый синтаксис закрытой виртуальной функции  
  
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
  
 В разделе [закрытые виртуальные функции](../dotnet/private-virtual-functions.md) для получения дополнительной информации.  
  
## <a name="clr-enum-type"></a>Тип перечисления Enum в среде CLR  
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
  
 Помимо этого незначительного изменения поведение типа перечисления CLR был изменен в следующих случаях:  
  
-   Опережающее объявление перечисления CLR больше не поддерживается.  
  
-   Разрешение перегрузки между встроенными арифметическими типами и иерархией классов объектов поменялись между управляемыми расширениями и Visual C++. Как побочный эффект перечислителях CLR больше не неявно преобразуются в арифметические типы.  
  
-   В новом синтаксисе перечисление CLR имеет собственную область видимости, которое не было в управляемых расширениях. Ранее перечислители отображались в области, содержащей перечисления. Теперь перечислители инкапсулируются в области перечисления.  
  
 В разделе [перечисляемый тип среды CLR](../dotnet/clr-enum-type.md) для получения дополнительной информации.  
  
## <a name="removal-of-box-keyword"></a>Удаление __box-зарезервированное слово  
 Упаковка-преобразование синтаксис управляемых расширений:  
  
```  
Object *o = __box( 1024 ); // explicit boxing  
```  
  
 Новый синтаксис упаковки-преобразования:  
  
```  
Object ^o = 1024; // implicit boxing  
```  
  
 В разделе [отслеживания обрабатывать значение упакованных](../dotnet/a-tracking-handle-to-a-boxed-value.md) для получения дополнительной информации.  
  
## <a name="pinning-pointer"></a>Закрепляющий указатель  
 Синтаксис закрепляющего указателя управляемых расширений:  
  
```  
__gc struct H { int j; };  
  
int main() {  
   H * h = new H;  
   int __pin * k = & h -> j;  
};  
```  
  
 Новый синтаксис закрепляющего указателя  
  
```  
ref struct H { int j; };  
  
int main() {  
   H^ h = gcnew H;  
   pin_ptr<int> k = &h->j;  
}  
```  
  
 В разделе [семантика типа значения](../dotnet/value-type-semantics.md) для получения дополнительной информации.  
  
## <a name="typeof-keyword-becomes-typeid"></a>typeid становится __typeof ключевое слово  
 Typeof синтаксис управляемых расширений:  
  
```  
Array* myIntArray =   
   Array::CreateInstance( __typeof(Int32), 5 );  
```  
  
 Новый синтаксис typeid:  
  
```  
Array^ myIntArray =   
   Array::CreateInstance( Int32::typeid, 5 );  
```  
  
 В разделе [переход typeof в T::typeid](../dotnet/typeof-goes-to-t-typeid.md) для получения дополнительной информации.  
  
## <a name="see-also"></a>См. также  
 [C + +/ CLI Основы миграции](../dotnet/cpp-cli-migration-primer.md)   
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)


