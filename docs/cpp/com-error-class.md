---
title: "Класс _com_error | Microsoft Docs"
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
  - "_com_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_com_error - класс"
ms.assetid: 70dafa69-b1fb-4a5c-9249-e857e0793d42
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс _com_error
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Объект `_com_error` представляет условие исключения, обнаруженное функциями оболочки обработки ошибок в файлах заголовков, создаваемых из библиотеки типов, или одним из классов поддержки COM.  Класс `_com_error` инкапсулирует код ошибки `HRESULT` и любой связанный объект `IErrorInfo Interface`.  
  
### Создание  
  
|||  
|-|-|  
|[\_com\_error](../cpp/com-error-com-error.md)|Создает объект `_com_error`.|  
  
### Операторы  
  
|||  
|-|-|  
|[operator \=](../cpp/com-error-operator-equal.md)|Присваивает существующий объект `_com_error` другому объекту.|  
  
### Функции извлечения  
  
|||  
|-|-|  
|[Ошибка](../Topic/_com_error::Error.md)|Получает элемент `HRESULT`, переданный конструктору.|  
|[ErrorInfo](../cpp/com-error-errorinfo.md)|Получает объект `IErrorInfo`, переданный конструктору.|  
|[WCode](../cpp/com-error-wcode.md)|Извлекает 16\-битный код ошибки, сопоставленный инкапсулированному значению `HRESULT`.|  
  
### Функции IErrorInfo  
  
|||  
|-|-|  
|[Описание](../cpp/com-error-description.md)|Вызывает функцию `IErrorInfo::GetDescription`.|  
|[HelpContext](../cpp/com-error-helpcontext.md)|Вызывает функцию `IErrorInfo::GetHelpContext`.|  
|[HelpFile](../Topic/_com_error::HelpFile.md)|Вызывает функцию `IErrorInfo::GetHelpFile`.|  
|[Исходный код](../cpp/com-error-source.md)|Вызывает функцию `IErrorInfo::GetSource`.|  
|[GUID](../cpp/com-error-guid.md)|Вызывает функцию `IErrorInfo::GetGUID`.|  
  
### Извлечение сообщения формата  
  
|||  
|-|-|  
|[ErrorMessage](../cpp/com-error-errormessage.md)|Получает строковое сообщение для значения HRESULT, хранящегося в объекте `_com_error`.|  
  
### Средства сопоставления ExepInfo.wCode с HRESULT  
  
|||  
|-|-|  
|[HRESULTToWCode](../cpp/com-error-hresulttowcode.md)|Сопоставляет 32\-разрядное значение `HRESULT` с 16\-разрядным `wCode`.|  
|[WCodeToHRESULT](../Topic/_com_error::WCodeToHRESULT.md)|Сопоставляет 16\-разрядное значение `wCode` с 32\-разрядным значением `HRESULT`.|  
  
## Завершение блока, относящегося только к системам Microsoft  
  
## Требования  
 `Header:` comdef.h  
  
 `Lib:` comsuppw.lib или comsuppwd.lib \(дополнительные сведения см. в разделе [\/Zc:wchar\_t \(wchar\_t – это собственный тип\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)\)  
  
## См. также  
 [Классы поддержки компилятора COM](../cpp/compiler-com-support-classes.md)   
 [IErrorInfo Interface](http://msdn.microsoft.com/ru-ru/4dda6909-2d9a-4727-ae0c-b5f90dcfa447)