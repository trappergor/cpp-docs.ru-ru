---
title: Класс _com_error | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error
dev_langs:
- C++
helpviewer_keywords:
- _com_error class
ms.assetid: 70dafa69-b1fb-4a5c-9249-e857e0793d42
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dfbaf1f0c88eaeb71bc4dfbbf2dca72c8d07251e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117443"
---
# <a name="comerror-class"></a>Класс _com_error

**Блок, относящийся только к системам Microsoft**

Объект **_com_error** представляет условие исключения, обнаруженное функциями оболочки обработки ошибок в файлах заголовков, создаваемых из библиотеки типов или одним из классов поддержки COM. **_Com_error** класс инкапсулирует код ошибки HRESULT и все связанные `IErrorInfo Interface` объекта.

### <a name="construction"></a>Создание экземпляра

|||
|-|-|
|[_com_error](../cpp/com-error-com-error.md)|Создает **_com_error** объекта.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[оператор =](../cpp/com-error-operator-equal.md)|Присвоение существующего **_com_error** объект с другим объектом.|

### <a name="extractor-functions"></a>Функции извлечения

|||
|-|-|
|[Ошибка](../cpp/com-error-error.md)|Возвращает значение HRESULT, переданный в конструктор.|
|[ErrorInfo](../cpp/com-error-errorinfo.md)|Получает объект `IErrorInfo`, переданный конструктору.|
|[WCode](../cpp/com-error-wcode.md)|Получает код ошибки 16-разрядное, сопоставленный в инкапсулированном виде HRESULT.|

### <a name="ierrorinfo-functions"></a>Функции IErrorInfo

|||
|-|-|
|[Описание](../cpp/com-error-description.md)|Вызывает функцию `IErrorInfo::GetDescription`.|
|[HelpContext](../cpp/com-error-helpcontext.md)|Вызывает функцию `IErrorInfo::GetHelpContext`.|
|[HelpFile](../cpp/com-error-helpfile.md)|Вызывает функцию `IErrorInfo::GetHelpFile`.|
|[Source](../cpp/com-error-source.md)|Вызывает функцию `IErrorInfo::GetSource`.|
|[GUID](../cpp/com-error-guid.md)|Вызывает функцию `IErrorInfo::GetGUID`.|

### <a name="format-message-extractor"></a>Извлечение сообщения формата

|||
|-|-|
|[ErrorMessage](../cpp/com-error-errormessage.md)|Получает строковое сообщение для значения HRESULT, хранящегося в **_com_error** объекта.|

### <a name="exepinfowcode-to-hresult-mappers"></a>Средства сопоставления ExepInfo.wCode с HRESULT

|||
|-|-|
|[HRESULTToWCode](../cpp/com-error-hresulttowcode.md)|Сопоставляется 16-разрядное в 32-разрядное значение HRESULT `wCode`.|
|[WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)|Сопоставляет 16-разрядный `wCode` 32-разрядное значение HRESULT.|

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="requirements"></a>Требования

**Заголовок:** \<comdef.h >

`Lib:` comsuppw.lib или comsuppwd.lib (см. в разделе [/Zc: wchar_t (wchar_t — собственный тип)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) Дополнительные сведения)

## <a name="see-also"></a>См. также

[Классы поддержки модели COM компилятора](../cpp/compiler-com-support-classes.md)<br/>
[Интерфейс IErrorInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo)