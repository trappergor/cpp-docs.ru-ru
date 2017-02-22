---
title: "_get_purecall_handler _set_purecall_handler | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_purecall_handler"
  - "_set_purecall_handler_m"
  - "_get_purecall_handler"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_set_purecall_handler"
  - "_set_purecall_handler_m"
  - "set_purecall_handler_m"
  - "set_purecall_handler"
  - "stdlib/_set_purecall_handler"
  - "stdlib/_get_purecall_handler"
  - "_get_purecall_handler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_set_purecall_handler - функция"
  - "set_purecall_handler - функция"
  - "purecall_handler"
  - "set_purecall_handler_m - функция"
  - "_purecall_handler"
  - "_set_purecall_handler_m - функция"
  - "функция _get_purecall_handler"
ms.assetid: 2759b878-8afa-4129-86e7-72afc2153d9c
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# _get_purecall_handler _set_purecall_handler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает или задает обработчик ошибок для вызова чистой виртуальной функции.  
  
## Синтаксис  
  
```  
typedef void (__cdecl* _purecall_handler)(void);  
  
_purecall_handler __cdecl _get_purecall_handler(void);  
  
_purecall_handler __cdecl _set_purecall_handler(   
   _purecall_handler function  
);  
```  
  
#### Параметры  
 `function`  
 Эту функцию необходимо вызывать при вызове чистой виртуальной функции. Функция `_purecall_handler` должна иметь тип возвращаемого значения void.  
  
## Возвращаемое значение  
 Предыдущая функция `_purecall_handler`. Возвращает `nullptr`, если не было предыдущего обработчика.  
  
## Заметки  
 `_get_purecall_handler` И `_set_purecall_handler` функции зависят от Microsoft и применяются только в коде C\+\+.  
  
 Вызов чистой виртуальной функции является ошибкой, поскольку он не имеет реализации. По умолчанию компилятор создает код для вызова функция обработчика ошибок при вызове чистой виртуальной функции, который завершает программу. Можно установить собственный обработчик ошибок для вызовов чисто виртуальную функцию перехватить их для отладки или отчетности. Чтобы использовать обработчик ошибок, создайте функцию, которая имеет `_purecall_handler` подпись, затем с помощью `_set_purecall_handler` вносить текущий обработчик.  
  
 Поскольку имеется только один `_purecall_handler` для каждого процесса, при вызове `_set_purecall_handler` немедленно влияет на все потоки. Последний вызывающий элемент в любом потоке задает обработчик.  
  
 Чтобы восстановить поведение по умолчанию, вызовите `_set_purecall_handler` с помощью `nullptr` аргумент.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_get_purecall_handler`, `_set_purecall_handler`|\< cstdlib \> или \< stdlib.h \>|  
  
 Сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// _set_purecall_handler.cpp  
// compile with: /W1  
#include <tchar.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
class CDerived;  
class CBase  
{  
public:  
   CBase(CDerived *derived): m_pDerived(derived) {};  
   ~CBase();  
   virtual void function(void) = 0;  
  
   CDerived * m_pDerived;  
};  
  
class CDerived : public CBase  
{  
public:  
   CDerived() : CBase(this) {};   // C4355  
   virtual void function(void) {};  
};  
  
CBase::~CBase()  
{  
   m_pDerived -> function();  
}  
  
void myPurecallHandler(void)  
{  
   printf("In _purecall_handler.");  
   exit(0);  
}  
  
int _tmain(int argc, _TCHAR* argv[])  
{  
   _set_purecall_handler(myPurecallHandler);  
   CDerived myDerived;  
}  
```  
  
```Output  
In _purecall_handler.  
```  
  
## См. также  
 [Обработка ошибок](../../c-runtime-library/error-handling-crt.md)   
 [\_purecall](../Topic/_purecall.md)