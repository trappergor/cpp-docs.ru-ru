---
title: новые возможности, gcnew ссылок (расширения компонентов C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- gcnew
- ref new
- gcnew_cpp
dev_langs:
- C++
helpviewer_keywords:
- ref new keyword (C++)
- gcnew keyword [C++]
ms.assetid: 388a62da-c2df-4a94-a9a2-205b53e577da
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9533675d2894b3c3d99e3fb57abded8ea4e99d7a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879065"
---
# <a name="ref-new-gcnew--c-component-extensions"></a>ref new, gcnew (расширения компонентов C++)
`ref new` Агрегатное ключевое слово выделяет экземпляр типа, который является мусора, когда объект становится недоступным, и возвращает дескриптор ([^](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)) выделенному объекту.  
  
## <a name="all-runtimes"></a>Все среды выполнения  
 Память для экземпляра типа, выделяемая `ref new`, освобождается автоматически.  
  
 Операция `ref new` вызывает `OutOfMemoryException`, если не удается выделить память.  
  
 Дополнительные сведения о том, как выделении и освобождении памяти для собственных типов C++ см. в разделе [новый и удаление операторов](../cpp/new-and-delete-operators.md).  
  
## <a name="windows-runtime"></a>Среда выполнения Windows  
 Используйте `ref new`, чтобы выделить память для объектов среды выполнения Windows, время существования которых требуется администрировать автоматически. Объект автоматически освобождается, когда число ссылок становится равным нулю, что происходит после выхода последней копии ссылки за пределы области. Дополнительные сведения см. в разделе [классы и структуры ссылки](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx).  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/ZW**  
  
## <a name="common-language-runtime"></a>Среда CLR 
 Память для управляемого типа (типа ссылки или значений) выделяется с помощью `gcnew` и освобождается с помощью сбора мусора.  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/clr**  
  
### <a name="examples"></a>Примеры  
 **Пример**  
  
 В следующем примере с помощью `gcnew` выделяется объект Message.  
  
```  
// mcppv2_gcnew_1.cpp  
// compile with: /clr  
ref struct Message {  
   System::String^ sender;  
   System::String^ receiver;  
   System::String^ data;  
};  
  
int main() {  
   Message^ h_Message  = gcnew Message;  
  //...  
}  
```  
  
 **Пример**  
  
 В следующем примере с помощью `gcnew` создается упакованный тип значения для использования в качестве ссылочного типа.  
  
```  
// example2.cpp : main project file.  
// compile with /clr  
using namespace System;  
value class Boxed {  
    public:  
        int i;  
};  
int main()  
{  
    Boxed^ y = gcnew Boxed;  
    y->i = 32;  
    Console::WriteLine(y->i);  
    return 0;  
}  
```  
  
 **Вывод**  
  
```Output  
32  
```  
  
## <a name="see-also"></a>См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)