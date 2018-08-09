---
title: typeid (расширения компонентов C++) | Документация Майкрософт
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
ms.openlocfilehash: 71087831b518e2aa4a2505023829781a610c867a
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011937"
---
# <a name="typeid--c-component-extensions"></a>typeid (расширения компонентов C++)
Получает значение, указывающее тип объекта.  
  
> [!WARNING]
>  Этот раздел относится к версии typeid расширений компонентов C++. Версии ISO C++ этого ключевого слова, см. в разделе [оператор typeid](../cpp/typeid-operator.md).  
  
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
 *T*  
 Имя типа.  
  
### <a name="remarks"></a>Примечания  
 В C + +/ CX, typeid возвращает [Platform::Type](../cppcx/platform-type-class.md) , созданный из сведений о типе среды выполнения.  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: `/ZW`  
  
## <a name="common-language-runtime"></a>Среда CLR 
### <a name="syntax"></a>Синтаксис  
  
```  
type::typeid  
```  
  
### <a name="parameters"></a>Параметры   
 *type*  
 Имя типа (абстрактный декларатор), для которого требуется `System::Type` объекта.  
  
### <a name="remarks"></a>Примечания  
  
 `typeid` используется для получения <xref:System.Type> для типа во время компиляции.  
  
 `typeid` Аналогично получению System::Type для типа во время выполнения с помощью <xref:System.Type.GetType%2A> или <xref:System.Object.GetType%2A>. Тем не менее typeid принимает только имени типа параметра.  Если вы хотите использовать для получения имени System::Type экземпляр типа, используйте GetType.  
  
 `typeid` должен иметь возможность оценить имени типа (тип) во время компиляции, тогда как GetType результатом является тип, возвращаемый во время выполнения.  
  
 `typeid` может занять имя собственного типа или общий псевдоним среды выполнения языка именем собственного типа; см. в разделе [эквиваленты в .NET Framework в собственные типы C++ (C + +/ CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md) Дополнительные сведения.  
  
 `typeid` Несмотря на то, что он будет по-прежнему возвращать System::Type также работает с собственными типами.  Чтобы получить структуру type_info, используйте [оператор typeid](../cpp/typeid-operator.md).  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: `/clr`  
  
### <a name="examples"></a>Примеры  
  
 В следующем примере сравниваются ключевое слово typeid `GetType()` член.  
  
```cpp  
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
  
```Output  
typeid and GetType returned the same System::Type  
G  
  
System.Single*  
```  
  
 Следующий пример показывает, что переменная типа System::Type можно использовать для получения атрибутов типа.  Он также показывает, что для некоторых типов, будет необходимо создать определение типа для использования `typeid`.  
  
```cpp  
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