---
title: _CRT_DISABLE_PERFCRIT_LOCKS
ms.date: 11/04/2016
f1_keywords:
- _CRT_DISABLE_PERFCRIT_LOCKS
- CRT_DISABLE_PERFCRIT_LOCKS
helpviewer_keywords:
- CRT_DISABLE_PERFCRIT_LOCKS constant
- _CRT_DISABLE_PERFCRIT_LOCKS constant
ms.assetid: 36cc2d86-cdb1-4b2b-a03c-c0d3818e7c6f
ms.openlocfilehash: b6f4d8dee5577e88aa59af9bff017aab0c7eef89
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57740265"
---
# <a name="crtdisableperfcritlocks"></a>_CRT_DISABLE_PERFCRIT_LOCKS

Отключает критическую с точки зрения производительности блокировку в операциях ввода-вывода.

## <a name="syntax"></a>Синтаксис

```
#define _CRT_DISABLE_PERFCRIT_LOCKS
```

## <a name="remarks"></a>Примечания

Определение этого символа может улучшить производительность в однопоточных привязанных к вводу-выводу программах путем принудительного использования однопоточной модели ввода-вывода во всех операциях ввода-вывода. Подробнее см. [Производительность многопоточных библиотек](../c-runtime-library/multithreaded-libraries-performance.md).

## <a name="see-also"></a>См. также

[Глобальные константы](../c-runtime-library/global-constants.md)
