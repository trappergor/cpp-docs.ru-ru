---
title: Классы поддержки компилятора COM | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_raise_error
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 6d800d9b-b902-4033-9639-740a30b06f88
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a3403a09700ba6f84792cc570d9fb093026241d8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070829"
---
# <a name="compiler-com-support-classes"></a>Классы поддержки компилятора COM

**Блок, относящийся только к системам Microsoft**

Стандартные классы используются для поддержки некоторых типов модели COM. Классы определены в \<comdef.h > и файлах заголовков, создаваемых из библиотеки типов.

|Класс|Цель|
|-----------|-------------|
|[_bstr_t](../cpp/bstr-t-class.md)|Создает программу оболочку для типа `BSTR`, предоставляя полезные операторы и методы.|
|[_com_error](../cpp/com-error-class.md)|Определяет объект ошибки, порождаемые [_com_raise_error](../cpp/com-raise-error.md) в случае большинства сбоев.|
|[_com_ptr_t](../cpp/com-ptr-t-class.md)|Инкапсулирует указатели COM-интерфейса и автоматически выполняет необходимые вызовы `AddRef`, `Release`, и `QueryInterface`.|
|[_variant_t](../cpp/variant-t-class.md)|Создает программу оболочку для типа `VARIANT`, предоставляя полезные операторы и методы.|

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Поддержка COM компилятора](../cpp/compiler-com-support.md)<br/>
[Глобальные функции COM-модели компилятора](../cpp/compiler-com-global-functions.md)<br/>
[Справочник по языку C++](../cpp/cpp-language-reference.md)