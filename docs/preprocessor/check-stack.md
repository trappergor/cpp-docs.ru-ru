---
title: Прагма check_stack
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.check_stack
- check_stack_CPP
helpviewer_keywords:
- check_stack pragma
- pragmas, check_stack
- pragmas, check_stack usage table
ms.assetid: f18e20cc-9abb-48b7-ad62-8d384875b996
ms.openlocfilehash: 4c976692ec36cedcb73825ee0cc7093736a3a3dc
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216137"
---
# <a name="check_stack-pragma"></a>Прагма check_stack

Указывает компилятору отключить зонды стека, если задано значение **Off** (или **-** ), или включить проверку стека, если задано значение **On** (или **+** ).

## <a name="syntax"></a>Синтаксис

> **#pragma check_stack (** [{ **On** | **Off** }] **)** \
> **#pragma check_stack** { **+**  |  **-** }

## <a name="remarks"></a>Примечания

Эта директива #pragma начинает действовать с первой функции, определенной после вхождения данной директивы. Стековые зонды не являются частью макросов или функций, создаваемых как встроенные.

Если не предоставить аргумент для директивы pragma **check_stack** , проверка стека вернется к поведению, указанному в командной строке. Дополнительные сведения см. в разделе [Параметры компилятора](../build/reference/compiler-options.md). В следующей таблице приведены `#pragma check_stack` сведения о взаимодействии параметров и параметра [/GS](../build/reference/gs-control-stack-checking-calls.md) .

### <a name="using-the-check_stack-pragma"></a>Использование директивы #pragma check_stack

|Синтаксис|Скомпилировано с использованием<br /><br /> параметра /Gs?|Действие|
|------------|------------------------------------|------------|
|`#pragma check_stack( )` или<br /><br /> `#pragma check_stack`|Да|Отключает проверку стека для последующих функций|
|`#pragma check_stack( )` или<br /><br /> `#pragma check_stack`|Нет|Включает проверку стека для последующих функций|
|`#pragma check_stack(on)`<br /><br /> ни`#pragma check_stack +`|"Да" или "Нет"|Включает проверку стека для последующих функций|
|`#pragma check_stack(off)`<br /><br /> ни`#pragma check_stack -`|"Да" или "Нет"|Отключает проверку стека для последующих функций|

## <a name="see-also"></a>См. также

[Директивы pragma и ключевое слово __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
