---
title: "_get_purecall_handler, _set_purecall_handler | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _set_purecall_handler
- _set_purecall_handler_m
- _get_purecall_handler
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _set_purecall_handler
- _set_purecall_handler_m
- set_purecall_handler_m
- set_purecall_handler
- stdlib/_set_purecall_handler
- stdlib/_get_purecall_handler
- _get_purecall_handler
dev_langs: C++
helpviewer_keywords:
- _set_purecall_handler function
- set_purecall_handler function
- purecall_handler
- set_purecall_handler_m function
- _purecall_handler
- _set_purecall_handler_m function
- _get_purecall_handler function
ms.assetid: 2759b878-8afa-4129-86e7-72afc2153d9c
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b32cf4e20be739f712cb9c0b0e0c8d3b0f0792ad
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="getpurecallhandler-setpurecallhandler"></a>_get_purecall_handler, _set_purecall_handler
Получает или задает обработчик ошибок для вызова чистой виртуальной функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef void (__cdecl* _purecall_handler)(void);  
  
_purecall_handler __cdecl _get_purecall_handler(void);  
  
_purecall_handler __cdecl _set_purecall_handler(   
   _purecall_handler function  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `function`  
 Эту функцию необходимо вызывать при вызове чистой виртуальной функции. Функция `_purecall_handler` должна иметь тип возвращаемого значения void.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Предыдущая функция `_purecall_handler`. Возвращает `nullptr`, если не было предыдущего обработчика.  
  
## <a name="remarks"></a>Примечания  
 Функции `_get_purecall_handler` и `_set_purecall_handler` предназначены специально для систем Майкрософт и применяются только к коду C++.  
  
 Вызов чистой виртуальной функции является ошибкой, так как она не имеет реализации. По умолчанию компилятор создает код для вызова функции обработчика ошибок при вызове чистой виртуальной функции, который завершает программу. Можно установить собственный обработчик ошибок для вызовов чисто виртуальных функций, который будет перехватывать их в целях отладки или ведения отчетности. Чтобы использовать собственный обработчик ошибок, создайте функцию с сигнатурой `_purecall_handler`, а затем с помощью `_set_purecall_handler` установите ее в качестве текущего обработчика.  
  
 Так как для каждого процесса существует только один обработчик `_purecall_handler`, при вызове функции `_set_purecall_handler` изменения немедленно применяются ко всем потокам. Последний вызывающий элемент в любом потоке задает обработчик.  
  
 Чтобы восстановить поведение по умолчанию, вызовите функцию `_set_purecall_handler` с аргументом `nullptr`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_get_purecall_handler`, `_set_purecall_handler`|\<cstdlib> или \<stdlib.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
  
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
  
## <a name="see-also"></a>См. также  
 [Обработка ошибок](../../c-runtime-library/error-handling-crt.md)   
 [_purecall](../../c-runtime-library/reference/purecall.md)