---
title: "Ошибка компилятора C2316 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2316
dev_langs: C++
helpviewer_keywords: C2316
ms.assetid: 9ad08eb5-060b-4eb0-8d66-0dc134f7bf67
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aed0e39ccfd320da6e6078f58a390a03e0ef08b5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2316"></a>Ошибка компилятора C2316

> "*исключение*": нельзя перехватить, поскольку деструктор или конструктор копии недоступны  
  
Исключение было перехвачено значением или ссылкой, но конструктор копии и оператор назначения были недоступны.  
  
Этот код был принят в версиях Visual C++ до Visual Studio 2003, но теперь он приводит к ошибке.  
  
Внесены изменения соответствия в Visual Studio 2015 ошибки применяются к инструкции catch неправильный исключений MFC, производный от `CException`. Поскольку `CException` имеет наследуемые закрытый конструктор копии, класс и его производные некопируемых и не могут передаваться по значению, поэтому также не может быть перехвачено значение. Инструкции, которые перехватываются исключения MFC ранее привело к неперехваченных исключений во время выполнения значение catch, но теперь компилятор правильно определяет этой проблеме и отчеты ошибка C2316. Чтобы устранить эту проблему, мы рекомендуем использовать макросы MFC TRY/CATCH, а не создавать собственные обработчики исключений, но если это не подходит для вашего кода, перехватывать исключения MFC по ссылке вместо него.   
  
## <a name="example"></a>Пример  
 При компиляции следующего примера возникнет ошибка C2316:  
  
```  
// C2316.cpp  
// compile with: /EHsc  
#include <stdio.h>  
  
extern "C" int printf_s(const char*, ...);  
  
struct B   
{  
public:  
    B() {}  
    // Delete the following line to resolve.  
private:  
    // copy constructor  
    B(const B&)   
    {  
    }  
};  
  
void f(const B&)   
{  
}  
  
int main()   
{  
    try   
    {  
        B aB;  
        f(aB);  
    }  
    catch (B b) {   // C2316  
        printf_s("Caught an exception!\n");     
    }  
}  
```