---
title: Производительность многопоточных библиотек | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- threading [C++], performance
- libraries, multithreaded
- performance, multithreading
- multithreaded libraries
ms.assetid: faa5d808-087c-463d-8f0d-8c478d137296
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9f66aebc7b6d77e3697fabf783332a83bdd6f3fb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052111"
---
# <a name="multithreaded-libraries-performance"></a>Производительность многопотоковых библиотек

Однопоточные CRT более не доступны. В этом разделе описано, как добиться максимальной производительности при использовании многопоточных библиотек.

## <a name="maximizing-performance"></a>Максимальное увеличение производительности

Производительность многопоточных библиотек улучшилась и близка к производительности теперь исключенных однопоточных библиотек. Для ситуаций, когда нужна еще более высокая производительность, предусмотрено несколько новых возможностей.

- Независимая блокировка потоков позволяет блокировать поток и применить [функции _nolock](../c-runtime-library/nolock-functions.md), которые получают доступ к потоку напрямую. Это позволяет использовать блокировки вне критических циклов.

- Языковой стандарт, задаваемый на уровне отдельных потоков, снижает стоимость доступа к языковому стандарту для многопоточных сценариев (см. [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md)).

- Функции, зависящие от языкового стандарта (имена которых оканчиваются на "_l "), принимают языковой стандарт в качестве параметра, что устраняет существенную часть затрат (например, [printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)).

- Оптимизации для общих кодовых страниц снижают стоимость множества коротких операций.

- Определение константы [_CRT_DISABLE_PERFCRIT_LOCKS](../c-runtime-library/crt-disable-perfcrit-locks.md) принудительно назначает модель однопоточного ввода-вывода для всех операций ввода-вывода и использование функций с версией _nolock. Это позволяет однопоточным приложениям, основанным в основном на вводе-выводе, получить более высокую производительность.

- Предоставление дескриптора кучи CRT позволяет включить кучу низкой фрагментации Windows (LFH) для кучи CRT, что может значительно повысить производительность в высокомасштабируемых сценариях.

## <a name="see-also"></a>См. также

[Функции библиотеки CRT](../c-runtime-library/crt-library-features.md)