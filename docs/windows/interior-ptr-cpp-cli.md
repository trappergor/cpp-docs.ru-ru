---
title: "interior_ptr (C + +/ CLI) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- stdcli::language::interior_ptr
- interior_ptr_cpp
- interior_ptr
dev_langs: C++
helpviewer_keywords: interior_ptr keyword [C++]
ms.assetid: 25160f74-569e-492d-9e3c-67ece7486baa
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cd3e79306cb97413a833e039b0b333cb85b8e56d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="interiorptr-ccli"></a>interior_ptr (C++/CLI)
*Внутренний указатель* объявляет указатель внутри ссылочного типа, но не на сам объект. Он может указывать на дескриптор ссылки, тип значения, дескриптор упакованного типа, член управляемого типа или элемент управляемого массива.  
  
## <a name="all-runtimes"></a>Все среды выполнения  
 (Отсутствуют комментарии для этой возможности языка, которая применяется во всех средах выполнения.)  
  
## <a name="windows-runtime"></a>Среда выполнения Windows  
 (Отсутствуют комментарии для этой возможности языка, которая применяется только в среде выполнения Windows).  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/ZW**  
  
## <a name="common-language-runtime"></a>Среда CLR  
 В следующем примере синтаксиса показан внутренний указатель.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
cli::interior_ptr<cv_qualifier type> var = &initializer;  
```  
  
### <a name="parameters"></a>Параметры  
 *cv_qualifier*  
 **const** или `volatile` квалификаторы.  
  
 *type*  
 Тип *инициализатора*.  
  
 *var*  
 Имя переменной `interior_ptr`.  
  
 *initializer*  
 Член ссылочного типа, элемент управляемого массива или любой другой объект, который можно присвоить собственному указателю.  
  
### <a name="remarks"></a>Примечания  
 Собственный указатель не может отслеживать элемент, если его расположение изменяется в управляемой куче в результате перемещения экземпляров объекта сборщиком мусора. Чтобы указатель правильно ссылался на экземпляр, среде выполнения необходимо обновить его, соориентировав на вновь расположенный объект.  
  
 `interior_ptr` представляет надмножество функциональности собственного указателя.  Таким образом, все, что можно присвоить собственному указателю, можно также присвоить указателю `interior_ptr`.  Внутреннему указателю разрешается выполнять тот же набор операций, что и собственному указателю, включая сравнение и вычисления с указателями.  
  
 Внутренний указатель можно объявлять только в стеке.  Его нельзя объявлять в качестве члена класса.  
  
 Поскольку внутренние указатели существуют только в стеке, при получении адреса внутреннего указателя создается неуправляемый указатель.  
  
 Указатель `interior_ptr` неявно преобразуется в тип `bool`, что позволяет использовать его в условных выражениях.  
  
 Сведения об объявлении внутреннего указателя, указывающего на объект, который не может быть перемещен в куче сбора мусора см. в разделе [pin_ptr](../windows/pin-ptr-cpp-cli.md).  
  
 `interior_ptr` находится в пространстве имен CLI.  В разделе [платформы, по умолчанию и пространства имен cli](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md) для получения дополнительной информации.  
  
 Дополнительные сведения о внутренних указателях см. в следующих разделах:  
  
-   [Практическое руководство. Объявление и использование внутренних указателей и управляемых массивов (C++/CLI)](../windows/how-to-declare-and-use-interior-pointers-and-managed-arrays-cpp-cli.md)  
  
-   [Практическое руководство. Объявление типов значений с использованием ключевого слова interior_ptr (C++/CLI)](../windows/how-to-declare-value-types-with-the-interior-ptr-keyword-cpp-cli.md)  
  
-   [Практическое руководство. Перегрузка функций с внутренними и собственными указателями (C++/CLI)](../windows/how-to-overload-functions-with-interior-pointers-and-native-pointers-cpp-cli.md)  
  
-   [Практическое руководство. Объявление внутренних указателей с использованием ключевого слова const (C++/CLI)](../windows/how-to-declare-interior-pointers-with-the-const-keyword-cpp-cli.md)  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/clr**  
  
### <a name="examples"></a>Примеры  
 **Пример**  
  
 В следующем примере показаны объявление и использование внутреннего указателя на ссылочный тип.  
  
```cpp  
// interior_ptr.cpp  
// compile with: /clr  
using namespace System;  
  
ref class MyClass {  
public:  
   int data;  
};  
  
int main() {  
   MyClass ^ h_MyClass = gcnew MyClass;  
   h_MyClass->data = 1;  
   Console::WriteLine(h_MyClass->data);  
  
   interior_ptr<int> p = &(h_MyClass->data);  
   *p = 2;  
   Console::WriteLine(h_MyClass->data);  
  
   // alternatively  
   interior_ptr<MyClass ^> p2 = &h_MyClass;  
   (*p2)->data = 3;  
   Console::WriteLine((*p2)->data);  
}  
```  
  
 **Вывод**  
  
```Output  
1  
2  
3  
```  
  
## <a name="see-also"></a>См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)