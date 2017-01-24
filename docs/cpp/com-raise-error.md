---
title: "_com_raise_error | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_raise_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_com_raise_error - функция"
ms.assetid: a98226c2-c3fe-44f1-8ff5-85863de11cd6
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_raise_error
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Создает ошибку [\_com\_error](../cpp/com-error-class.md) в ответ на сбой.  
  
## Синтаксис  
  
```  
  
      void __stdcall _com_raise_error(  
   HRESULT hr,  
   IErrorInfo* perrinfo = 0  
);  
```  
  
#### Параметры  
 `hr`  
 Информация о значении `HRESULT`.  
  
 `perrinfo`  
 Объект **IErrorInfo**.  
  
## Заметки  
 Параметр `_com_raise_error`, заданный в comdef.h, можно заменить пользовательской версией с тем же именем и прототипом.  Это можно сделать, если требуется использовать `#import` без обработки исключений C\+\+.  В этом случае пользовательская версия **\_com\_raise\_error** может решить выполнить `longjmp` или отобразить окно сообщения и остановить выполнение.  Однако пользовательская версия не должна возвращаться, поскольку код поддержки COM в компиляторе не ожидает ее возврата.  
  
 Также можно использовать [\_set\_com\_error\_handler](../cpp/set-com-error-handler.md) для замены функции обработки ошибок по умолчанию.  
  
 По умолчанию `_com_raise_error` определяется следующим образом.  
  
```  
void __stdcall _com_raise_error(HRESULT hr, IErrorInfo* perrinfo) {  
   throw _com_error(hr, perrinfo);  
}  
```  
  
## Завершение блока, относящегося только к системам Microsoft  
  
## Требования  
 **Заголовок:** comdef.h  
  
 **Lib.** Если параметр компилятора "wchar\_t — собственный тип" включен, используйте comsuppw.lib или comsuppwd.lib.  Если этот параметр отключен, используйте comsupp.lib.  Дополнительные сведения см. в разделе [\/Zc:wchar\_t \(wchar\_t – это собственный тип\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).  
  
## См. также  
 [Глобальные функции компилятора COM](../cpp/compiler-com-global-functions.md)   
 [\_set\_com\_error\_handler](../cpp/set-com-error-handler.md)