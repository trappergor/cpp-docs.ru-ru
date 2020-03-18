---
title: Классы поддержки компилятора COM
ms.date: 11/04/2016
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 6d800d9b-b902-4033-9639-740a30b06f88
ms.openlocfilehash: 1a9ff7c57965c9ba00881d5fe48501a6138b31d1
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79444430"
---
# <a name="compiler-com-support-classes"></a>Классы поддержки компилятора COM

**Блок, относящийся только к системам Microsoft**

Стандартные классы используются для поддержки некоторых типов модели COM. Классы определяются в \<comdef. h > и файлы заголовков, созданные из библиотеки типов.

|Class|Назначение|
|-----------|-------------|
|[_bstr_t](../cpp/bstr-t-class.md)|Создает программу оболочку для типа `BSTR`, предоставляя полезные операторы и методы.|
|[_com_error](../cpp/com-error-class.md)|Определяет объект Error, вызываемый [_com_raise_error](../cpp/com-raise-error.md) в большинстве сбоев.|
|[_com_ptr_t](../cpp/com-ptr-t-class.md)|Инкапсулирует указатели на COM-интерфейсы и автоматизирует необходимые вызовы `AddRef`, `Release`и `QueryInterface`.|
|[_variant_t](../cpp/variant-t-class.md)|Создает программу оболочку для типа `VARIANT`, предоставляя полезные операторы и методы.|

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Поддержка COM компилятора](../cpp/compiler-com-support.md)<br/>
[Глобальные функции COM-модели компилятора](../cpp/compiler-com-global-functions.md)<br/>
[Справочник по языку C++](../cpp/cpp-language-reference.md)