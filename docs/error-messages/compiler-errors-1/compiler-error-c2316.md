---
title: Ошибка компилятора C2316 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2316
dev_langs:
- C++
helpviewer_keywords:
- C2316
ms.assetid: 9ad08eb5-060b-4eb0-8d66-0dc134f7bf67
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 895db6535299a077bc32b6485a360ae450e6c87e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33196848"
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