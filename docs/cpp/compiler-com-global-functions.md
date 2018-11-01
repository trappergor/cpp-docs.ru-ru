---
title: Глобальные функции COM-модели компилятора
ms.date: 11/04/2016
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 74449d26-50a2-47c7-b175-7cf2cf83533e
ms.openlocfilehash: ac74270cd020aa66ccc14ff314a00b388a038086
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50504434"
---
# <a name="compiler-com-global-functions"></a>Глобальные функции COM-модели компилятора

**Блок, относящийся только к системам Microsoft**

Доступны следующие процедуры.

|Функция|Описание|
|--------------|-----------------|
|[_com_raise_error](../cpp/com-raise-error.md)|Создает [_com_error](../cpp/com-error-class.md) в ответ на сбой.|
|[_set_com_error_handler](../cpp/set-com-error-handler.md)|Заменяет функцию по умолчанию, используемую для обработки ошибок COM.|
|[ConvertBSTRToString](../cpp/convertbstrtostring.md)|Преобразует `BSTR` значение `char *`.|
|[ConvertStringToBSTR](../cpp/convertstringtobstr.md)|Преобразует `char *` значение `BSTR`.|

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Классы поддержки модели COM компилятора](../cpp/compiler-com-support-classes.md)<br/>
[Поддержка COM компилятора](../cpp/compiler-com-support.md)