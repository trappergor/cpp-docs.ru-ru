---
title: Препроцессор
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor
ms.assetid: e120eda3-b413-49f1-a07c-e9fb128cf500
ms.openlocfilehash: 7188d7a6803c9eec109a59906cf0c016a460819d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337509"
---
# <a name="preprocessor"></a>Препроцессор

Препроцессор — это текстовый процессор, управляющий текстом файла исходного кода в ходе первого этапа трансляции. Препроцессор не разбирает исходный текст, но он разбивает его на токены, чтобы найти макрозвонки. Хотя компилятор обычно вызывает препроцессор при первом проходе, препроцессор можно также вызвать отдельно для обработки текста без его компиляции.

Справочные материалы по препроцессору содержат следующие разделы:

- [Директивы препроцессора](../preprocessor/preprocessor-directives.md)

- [Операторы препроцессора](../preprocessor/preprocessor-operators.md)

- [Предопределенные макросы](../preprocessor/predefined-macros.md)

- [Директивы pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)

**Microsoft Специфический**

Вы можете получить список исходного кода после предварительной обработки с помощью опции компилятора [/E](../build/reference/e-preprocess-to-stdout.md) или [EP.](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) Оба варианта вызывают предварительный процессор и отправляют полученный текст на стандартное выходное устройство, которое в большинстве случаев является консолью. Разница между этими двумя `/E` `#line` вариантами заключается в том, что включает в себя директивы и `/EP` исключает эти директивы.

**END Microsoft Специфический**

## <a name="special-terminology"></a><a name="_predir_special_terminology"></a>Специальная терминология

В документации препроцессора термин "аргумент" означает сущность, передаваемую в функцию. В некоторых случаях он изменяется "фактическим" или "формальным", который описывает выражение аргумента, указанное в вызове функции, и декларацию аргумента, указанную в определении функции, соответственно.

Термин "переменная" обозначает простой объект данных C-типа. Термин «объект» относится как к объектам, так и к переменным; это инклюзивный термин.

## <a name="see-also"></a>См. также раздел

[Допроцессорная ссылка на C/C](../preprocessor/c-cpp-preprocessor-reference.md)\
[Фазы трансляции](../preprocessor/phases-of-translation.md)
