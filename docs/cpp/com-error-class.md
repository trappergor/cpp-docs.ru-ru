---
title: "Класс _com_error | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error
dev_langs: C++
helpviewer_keywords: _com_error class
ms.assetid: 70dafa69-b1fb-4a5c-9249-e857e0793d42
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 47ee4686c5c0a239b868d6da9aaccc332def19dc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="comerror-class"></a>Класс _com_error
**Блок, относящийся только к системам Microsoft**  
  
 Объект `_com_error` представляет условие исключения, обнаруженное функциями оболочки обработки ошибок в файлах заголовков, создаваемых из библиотеки типов, или одним из классов поддержки COM. Класс `_com_error` инкапсулирует код ошибки `HRESULT` и любой связанный объект `IErrorInfo Interface`.  
  
### <a name="construction"></a>Создание экземпляра  
  
|||  
|-|-|  
|[_com_error](../cpp/com-error-com-error.md)|Создает объект `_com_error`.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор =](../cpp/com-error-operator-equal.md)|Присваивает существующий объект `_com_error` другому объекту.|  
  
### <a name="extractor-functions"></a>Функции извлечения  
  
|||  
|-|-|  
|[Ошибка](../cpp/com-error-error.md)|Получает элемент `HRESULT`, переданный конструктору.|  
|[ErrorInfo](../cpp/com-error-errorinfo.md)|Получает объект `IErrorInfo`, переданный конструктору.|  
|[WCode](../cpp/com-error-wcode.md)|Извлекает 16-битный код ошибки, сопоставленный инкапсулированному значению `HRESULT`.|  
  
### <a name="ierrorinfo-functions"></a>Функции IErrorInfo  
  
|||  
|-|-|  
|[Описание](../cpp/com-error-description.md)|Вызывает функцию `IErrorInfo::GetDescription`.|  
|[HelpContext](../cpp/com-error-helpcontext.md)|Вызывает функцию `IErrorInfo::GetHelpContext`.|  
|[Файл справки](../cpp/com-error-helpfile.md)|Вызывает функцию `IErrorInfo::GetHelpFile`.|  
|[Source](../cpp/com-error-source.md)|Вызывает функцию `IErrorInfo::GetSource`.|  
|[GUID](../cpp/com-error-guid.md)|Вызывает функцию `IErrorInfo::GetGUID`.|  
  
### <a name="format-message-extractor"></a>Извлечение сообщения формата  
  
|||  
|-|-|  
|[Сообщение об ошибке](../cpp/com-error-errormessage.md)|Получает строковое сообщение для значения HRESULT, хранящегося в объекте `_com_error`.|  
  
### <a name="exepinfowcode-to-hresult-mappers"></a>Средства сопоставления ExepInfo.wCode с HRESULT  
  
|||  
|-|-|  
|[HRESULTToWCode](../cpp/com-error-hresulttowcode.md)|Сопоставляет 32-разрядный `HRESULT` с 16-разрядным `wCode`.|  
|[WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)|Сопоставляет 16-разрядный `wCode` с 32-разрядным `HRESULT`.|  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** comdef.h  
  
 `Lib:`comsuppw.lib или comsuppwd.lib (в разделе [/Zc: wchar_t (wchar_t – это собственный тип)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) для получения дополнительной информации)  
  
## <a name="see-also"></a>См. также  
 [Классы поддержки компилятора COM](../cpp/compiler-com-support-classes.md)   
 [Интерфейс IErrorInfo](http://msdn.microsoft.com/en-us/4dda6909-2d9a-4727-ae0c-b5f90dcfa447)