---
title: '-Zc: auto (выведение типа переменной) | Документация Майкрософт'
ms.custom: ''
ms.date: 02/28/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zc:auto
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- Deduce variable type (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 5f5bc102-44c3-4688-bbe1-080594dcee5c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b306a104b9f71d536684e62f6dda1cac45b1d9dd
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42612945"
---
# <a name="zcauto-deduce-variable-type"></a>/Zc:auto (выведение типа переменной)

**/Zc: auto [-]** параметр компилятора сообщает компилятору, как использовать [ключевое слово auto](../../cpp/auto-keyword.md) для объявления переменных. При использовании параметра по умолчанию, **/Zc: auto**, компилятор выводит тип объявленной переменной из выражения инициализации. Если указать **/Zc:auto-**, компилятор выделяет переменную для автоматического класса хранения.

## <a name="syntax"></a>Синтаксис

> **/ Zc: auto**[**-**]  

## <a name="remarks"></a>Примечания

Стандарт языка C++ определяет первоначальное и измененное значение ключевого слова `auto`. До Visual C++ 2010 ключевое слово объявляло переменную в автоматическом классе хранения; то есть, то есть переменную с локальным временем существования. Начиная с Visual C++ 2010, ключевое слово выводит тип переменной из выражения инициализации объявления. Используйте **/Zc: auto [-]** параметр компилятора, чтобы сообщить компилятору на необходимость использования первоначального или измененного значения `auto` ключевое слово. **/Zc: auto** включен параметр по умолчанию. [/ Permissive-](permissive-standards-conformance.md) параметр не меняет значение по умолчанию **/Zc: auto**.

Компилятор выдает соответствующее диагностическое сообщение, если использование `auto` ключевое слово противоречит текущего **/Zc: auto** параметр компилятора. Дополнительные сведения см. в разделе [ключевое слово auto](../../cpp/auto-keyword.md). Дополнительные сведения о вопросах соответствия в Visual C++, см. в разделе [нестандартное поведение](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Установка параметра компилятора в Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **командной строки** страницу свойств.

1. Добавить **/Zc: auto** или **/Zc:auto-** для **Дополнительные параметры:** области.

## <a name="see-also"></a>См. также

[/Zc (соответствие)](../../build/reference/zc-conformance.md)<br/>
[Ключевое слово auto](../../cpp/auto-keyword.md)
