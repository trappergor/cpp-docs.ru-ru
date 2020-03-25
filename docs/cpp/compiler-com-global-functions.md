---
title: Глобальные функции COM-модели компилятора
ms.date: 11/04/2016
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 74449d26-50a2-47c7-b175-7cf2cf83533e
ms.openlocfilehash: c0a9c742ad9dcbb05ed2d78c954d5a597e3b57cb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189784"
---
# <a name="compiler-com-global-functions"></a>Глобальные функции COM-модели компилятора

**Блок, относящийся только к системам Microsoft**

Доступны следующие процедуры.

|Компонент|Description|
|--------------|-----------------|
|[_com_raise_error](../cpp/com-raise-error.md)|Вызывает исключение [_com_error](../cpp/com-error-class.md) в ответ на сбой.|
|[_set_com_error_handler](../cpp/set-com-error-handler.md)|Заменяет функцию по умолчанию, используемую для обработки ошибок COM.|
|[ConvertBSTRToString](../cpp/convertbstrtostring.md)|Преобразует значение типа `BSTR` в значение типа `char *`.|
|[ConvertStringToBSTR](../cpp/convertstringtobstr.md)|Преобразует значение типа `char *` в значение типа `BSTR`.|

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Классы поддержки модели COM компилятора](../cpp/compiler-com-support-classes.md)<br/>
[Поддержка COM компилятора](../cpp/compiler-com-support.md)
