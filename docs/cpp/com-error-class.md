---
title: Класс _com_error
ms.date: 11/04/2016
f1_keywords:
- _com_error
helpviewer_keywords:
- _com_error class
ms.assetid: 70dafa69-b1fb-4a5c-9249-e857e0793d42
ms.openlocfilehash: 828a1ec68fef631700d5b64e6aeeec6660acf9a8
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498742"
---
# <a name="_com_error-class"></a>Класс _com_error

**Блок, относящийся только к системам Microsoft**

Объект **_com_error** представляет условие исключения, обнаруженное функциями-оболочками обработки ошибок в файлах заголовков, созданных из библиотеки типов или одним из классов поддержки COM. Класс **_com_error** инкапсулирует код ошибки HRESULT и любой связанный `IErrorInfo Interface` объект.

### <a name="construction"></a>Создание экземпляра

|||
|-|-|
|[_com_error](../cpp/com-error-com-error.md)|Конструирует объект **_com_error** .|

### <a name="operators"></a>Операторы

|||
|-|-|
|[Оператор =](../cpp/com-error-operator-equal.md)|Присваивает существующий объект **_com_error** другому объекту.|

### <a name="extractor-functions"></a>Функции извлечения

|||
|-|-|
|[Ошибка](../cpp/com-error-error.md)|Извлекает значение HRESULT, передаваемое конструктору.|
|[ErrorInfo](../cpp/com-error-errorinfo.md)|Получает объект `IErrorInfo`, переданный конструктору.|
|[WCode](../cpp/com-error-wcode.md)|Извлекает 16-разрядный код ошибки, сопоставленный с инкапсулированным значением HRESULT.|

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
|[ErrorMessage](../cpp/com-error-errormessage.md)|Извлекает строковое сообщение для HRESULT, хранящегося в объекте **_com_error** .|

### <a name="exepinfowcode-to-hresult-mappers"></a>Средства сопоставления ExepInfo.wCode с HRESULT

|||
|-|-|
|[хресулттовкоде](../cpp/com-error-hresulttowcode.md)|Сопоставляет 32-разрядное значение HRESULT с 16 `wCode`-разрядным.|
|[вкодетохресулт](../cpp/com-error-wcodetohresult.md)|Сопоставляет 16-бит `wCode` с 32-битным значением HRESULT.|

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="requirements"></a>Требования

**Заголовок:** \<> comdef. h

`Lib:`комсуппв. lib или комсуппвд. lib (Дополнительные сведения см. в разделе [/Zc: wchar_t (wchar_t Native Type)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) )

## <a name="see-also"></a>См. также

[Классы поддержки модели COM компилятора](../cpp/compiler-com-support-classes.md)<br/>
[Интерфейс IErrorInfo](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo)