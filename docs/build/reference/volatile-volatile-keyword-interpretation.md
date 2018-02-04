---
title: "-volatile (Интерпретация ключевого слова volatile) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /volatile:iso
- /volatile:ms
- /volatile
dev_langs:
- C++
helpviewer_keywords:
- /volatile compiler option
- /volatile compiler option [C++]
- -volatile compiler option
- volatile compiler option [C++]
- volatile compiler option
- -volatile compiler option [C++]
ms.assetid: 9d08fcc6-5bda-44c8-8151-8d8d54f164b8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4528d53da01ae83f179f07ba52b2c86c335e883c
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2018
---
# <a name="volatile-volatile-keyword-interpretation"></a>/volatile (интерпретация ключевого слова volatile)

Указывает, как [volatile](../../cpp/volatile-cpp.md) ключевое слово будет интерпретироваться.

## <a name="syntax"></a>Синтаксис

> **/volatile:**{**iso**|**ms**}  

## <a name="arguments"></a>Аргументы

**/volatile:ISO**  
Выбирает strict `volatile` семантику в соответствии с языком C++ в соответствии со стандартом ISO. Семантика получения и освобождения не гарантируется при переменном обращении. Если компилятор ARM, это Интерпретация по умолчанию `volatile`.

**/volatile:ms**  
Выбирает расширенные Майкрософт `volatile` семантику, которая добавить память, приоритет очередности за пределы языка C++ стандарта ISO. Семантика получения и освобождения гарантируется при переменном обращении. Тем не менее этот параметр также предписывает компилятору создавать барьеры памяти оборудования, что может увеличить значительных временных затрат на ARM и других архитектур слабое упорядочение в памяти. Если компилятор предназначен для любой платформы, кроме ARM, это по умолчанию интерпретацию `volatile`.

## <a name="remarks"></a>Примечания

Мы настоятельно рекомендуем использовать **/volatile:iso** вместе с явные примитивы синхронизации и встроенные функции компилятора при работе с памятью, совместно используемой потоками. Дополнительные сведения см. в разделе [volatile](../../cpp/volatile-cpp.md).

При переносе существующего кода, или изменить этот параметр в середине проекта, может оказаться полезным включить предупреждение [C4746](../../error-messages/compiler-warnings/compiler-warning-c4746.md) для определения места кода, затрагиваемые разности в семантике.

Имеется не `#pragma` эквивалентное значению этого параметра.

### <a name="to-set-the-volatile-compiler-option-in-visual-studio"></a>Чтобы задать / volatile-параметр компилятора в Visual Studio

1. Откройте **страницы свойств** диалоговое окно для проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **командной строки** страницу свойств.

1. В **Дополнительные параметры** добавьте **/volatile:iso** или **/volatile:ms** и выберите **ОК** или **применить** для сохранения изменений.

## <a name="see-also"></a>См. также

[volatile](../../cpp/volatile-cpp.md)  
[Параметры компилятора](../../build/reference/compiler-options.md)  
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)  
