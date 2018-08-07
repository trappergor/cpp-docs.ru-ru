---
title: New (новый слот в vtable) (расширения компонентов C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- new keyword [C++]
ms.assetid: 1a9a5704-f02f-46ae-ad65-f0f2b6dbabc3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 32452b4fd44aed2bc399165b3184d974f22d90b6
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39607015"
---
# <a name="new-new-slot-in-vtable--c-component-extensions"></a>new (новый слот в vtable) (расширения компонентов C++)
**Новый** слово указывает, что виртуальный член получает новую ячейку в таблице vtable.  
  
## <a name="all-runtimes"></a>Все среды выполнения  
 (Отсутствуют комментарии для этой возможности языка, которая применяется во всех средах выполнения.)  
  
## <a name="windows-runtime"></a>Среда выполнения Windows  
 Не поддерживается в среде выполнения Windows.  
  
## <a name="common-language-runtime"></a>Среда CLR 
### <a name="remarks"></a>Примечания  
  
 В `/clr` компиляции **новый** указывает, что виртуальный член получает новую ячейку в таблице vtable, что функция не переопределяет метод базового класса.  
  
 **новый** вызывает модификатор newslot добавляемый IL-код для функции.  Дополнительные сведения о newslot см. в разделе:  
  
-   [Метод MethodInfo.GetBaseDefinition](https://msdn.microsoft.com/library/system.reflection.methodinfo.getbasedefinition.aspx)  
  
-   [Перечисление пространство](https://msdn.microsoft.com/library/system.reflection.methodattributes.aspx)  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: `/clr`  
  
### <a name="examples"></a>Примеры  
  
 В следующем примере показано влияние **новый**.  
  
```cpp  
// newslot.cpp  
// compile with: /clr  
ref class C {  
public:  
   virtual void f() {  
      System::Console::WriteLine("C::f() called");  
   }  
  
   virtual void g() {  
      System::Console::WriteLine("C::g() called");  
   }  
};  
  
ref class D : public C {  
public:  
   virtual void f() new {  
      System::Console::WriteLine("D::f() called");  
   }  
  
   virtual void g() override {  
      System::Console::WriteLine("D::g() called");  
   }  
};  
  
ref class E : public D {  
public:  
   virtual void f() override {  
      System::Console::WriteLine("E::f() called");  
   }  
};  
  
int main() {  
   D^ d = gcnew D;  
   C^ c = gcnew D;  
  
   c->f();   // calls C::f  
   d->f();   // calls D::f  
  
   c->g();   // calls D::g  
   d->g();   // calls D::g  
  
   D ^ e = gcnew E;  
   e->f();   // calls E::f  
}  
```  
  
 **Вывод**  
  
```Output  
C::f() called  
  
D::f() called  
  
D::g() called  
  
D::g() called  
  
E::f() called  
```  
  
## <a name="see-also"></a>См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)   
 [Спецификаторы переопределения](../windows/override-specifiers-cpp-component-extensions.md)