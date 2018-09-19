---
title: Глобальные функции COM компилятора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 74449d26-50a2-47c7-b175-7cf2cf83533e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cb769cf1419f7a0142a5eeae348ca432f78fb92a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034145"
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