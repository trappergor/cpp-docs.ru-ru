---
title: Класс _com_error
ms.date: 11/04/2016
f1_keywords:
- _com_error
helpviewer_keywords:
- _com_error class
ms.assetid: 70dafa69-b1fb-4a5c-9249-e857e0793d42
ms.openlocfilehash: 8ed1521cbf768e5b473281e5f9b7c6597cdc4692
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155206"
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
|[Источник](../cpp/com-error-source.md)|Вызывает функцию `IErrorInfo::GetSource`.|
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
[Интерфейс IErrorInfo](/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo)