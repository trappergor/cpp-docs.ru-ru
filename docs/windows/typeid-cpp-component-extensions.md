---
title: typeid (расширения компонентов C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- typeid keyword [C++]
ms.assetid: e9706cae-e7c4-4d6d-b474-646d73df3e70
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: db1efac0a38aaa11238452e418277f78dbcd6d9d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="typeid--c-component-extensions"></a>typeid (расширения компонентов C++)
Возвращает значение, указывающее тип объекта.  
  
> [!WARNING]
>  Этот раздел относится к версии typeid расширений компонентов C++. Версии ISO C++ это ключевое слово, см. [оператор typeid](../cpp/typeid-operator.md).  
  
## <a name="all-runtimes"></a>Все среды выполнения  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
T::typeid  
```  
  
### <a name="parameters"></a>Параметры  
 *T*  
 Имя типа.  
  
## <a name="windows-runtime"></a>Среда выполнения Windows  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
Platform::Type^ type = T::typeid;  
```  
  
### <a name="parameters"></a>Параметры  
 `T`  
 Имя типа.  
  
### <a name="remarks"></a>Примечания  
 В C + +/ CX typeid возвращает [Platform::Type](../cppcx/platform-type-class.md) , создается на основе сведений о типе среды выполнения.  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/ZW**  
  
## <a name="common-language-runtime"></a>Среда CLR 
 **Синтаксис**  
  
```  
  
type::typeid  
```  
  
 **Параметры**  
  
 *type*  
 Имя типа (абстрактный декларатор), для которого требуется объект System::Type.  
  
 **Заметки**  
  
 `typeid` используется для получения <xref:System.Type> для типа во время компиляции.  
  
 `typeid` Аналогично получению System::Type для типа во время выполнения с помощью <xref:System.Type.GetType%2A> или <xref:System.Object.GetType%2A>. Однако typeid принимает только имя типа параметра.  Если вы хотите использовать для получения имени System::Type экземпляр типа, используйте GetType.  
  
 `typeid` необходима возможность вычислять имени типа (тип) во время компиляции, в то время как GetType результатом является тип, возвращаемый во время выполнения.  
  
 `typeid` может принимать имя собственного типа или общий псевдоним языка среды выполнения для имени собственного типа; в разделе [эквиваленты C++ собственных типов .NET Framework (C + +/ CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md) для получения дополнительной информации.  
  
 `typeid` Несмотря на то, что он будет по-прежнему возвращать System::Type также работает с собственных типов.  Чтобы получить структуру type_info, используйте [оператор typeid](../cpp/typeid-operator.md).  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/clr**  
  
### <a name="examples"></a>Примеры  
 **Пример**  
  
 В следующем примере сравниваются ключевое слово typeid GetType() член.  
  
```  
// keyword__typeid.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct G {  
   int i;  
};  
  
int main() {  
   G ^ pG = gcnew G;  
   Type ^ pType = pG->GetType();  
   Type ^ pType2 = G::typeid;  
  
   if (pType == pType2)  
      Console::WriteLine("typeid and GetType returned the same System::Type");  
   Console::WriteLine(G::typeid);  
  
   typedef float* FloatPtr;  
   Console::WriteLine(FloatPtr::typeid);  
}  
```  
  
 **Вывод**  
  
```Output  
typeid and GetType returned the same System::Type  
G  
  
System.Single*  
  
```  
  
 **Пример**  
  
 Следующий пример показывает, что переменная типа System::Type можно использовать для получения атрибутов типа.  Здесь также показано, что для некоторых типов, необходимо будет создать typedef для использования `typeid`.  
  
```  
// keyword__typeid_2.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Security;  
using namespace System::Security::Permissions;  
  
typedef int ^ handle_to_int;  
typedef int * pointer_to_int;  
  
public ref class MyClass {};  
  
class MyClass2 {};  
  
[attribute(AttributeTargets::All)]  
ref class AtClass {  
public:  
   AtClass(Type ^) {  
      Console::WriteLine("in AtClass Type ^ constructor");  
   }  
};  
  
[attribute(AttributeTargets::All)]  
ref class AtClass2 {  
public:  
   AtClass2() {  
      Console::WriteLine("in AtClass2 constructor");  
   }  
};  
  
// Apply the AtClass and AtClass2 attributes to class B  
[AtClass(MyClass::typeid), AtClass2]     
[AttributeUsage(AttributeTargets::All)]  
ref class B : Attribute {};  
  
int main() {  
   Type ^ MyType = B::typeid;  
  
   Console::WriteLine(MyType->IsClass);  
  
   array<Object^>^ MyArray = MyType -> GetCustomAttributes(true);  
   for (int i = 0 ; i < MyArray->Length ; i++ )  
      Console::WriteLine(MyArray[i]);  
  
   if (int::typeid != pointer_to_int::typeid)  
      Console::WriteLine("int::typeid != pointer_to_int::typeid, as expected");  
  
   if (int::typeid == handle_to_int::typeid)  
      Console::WriteLine("int::typeid == handle_to_int::typeid, as expected");  
}  
```  
  
 **Вывод**  
  
```Output  
True  
  
in AtClass2 constructor  
  
in AtClass Type ^ constructor  
  
AtClass2  
  
System.AttributeUsageAttribute  
  
AtClass  
  
int::typeid != pointer_to_int::typeid, as expected  
  
int::typeid == handle_to_int::typeid, as expected  
```  
  
## <a name="see-also"></a>См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)