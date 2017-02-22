---
title: "_com_error::WCode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_error.WCode"
  - "_com_error::WCode"
  - "WCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WCode - метод"
ms.assetid: f3b21852-f8ea-4e43-bff1-11c2d35454c4
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_error::WCode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Извлекает 16\-битный код ошибки, сопоставленный инкапсулированному значению `HRESULT`.  
  
## Синтаксис  
  
```  
  
WORD WCode ( ) const throw( );  
  
```  
  
## Возвращаемое значение  
 Если значение `HRESULT` лежит в пределах диапазона от 0x80040200 до 0x8004FFFF, метод **WCode** возвращает значение `HRESULT` минус 0x80040200; в противном случае возвращается ноль.  
  
## Заметки  
 Метод **WCode** используется для отмены сопоставления, выполняемого в коде поддержки COM.  Оболочка свойства или метода **dispinterface** вызывает вспомогательную процедуру, которая упаковывает аргументы и вызывает **IDispatch::Invoke**.  Если при возврате возвращается сбойное значение `HRESULT` `DISP_E_EXCEPTION`, информация об ошибке извлекается из структуры **EXCEPINFO**, переданной в **IDispatch::Invoke**.  Код ошибки может быть 16\-разрядным значением, хранящимся в члене `wCode` структуры **EXCEPINFO**, или полным 32\-разрядным значением, хранящимся в члене **scode** структуры **EXCEPINFO**.  Если возвращен 16\-разрядный код `wCode`, его необходимо сначала сопоставить 32\-разрядному коду сбоя `HRESULT`.  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [\_com\_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)   
 [\_com\_error::WCodeToHRESULT](../Topic/_com_error::WCodeToHRESULT.md)   
 [Класс \_com\_error](../cpp/com-error-class.md)