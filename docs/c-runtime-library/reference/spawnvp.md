---
title: spawnvp
ms.date: 12/16/2019
api_name:
- spawnvp
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- spawnvp
helpviewer_keywords:
- spawnvp function
ms.assetid: 25d3896d-1934-4453-ae8b-4fb5480a2657
ms.openlocfilehash: a1a3bb4d5220810ecdea9fb3bad07a88f7eb17cf
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75300681"
---
# <a name="spawnvp"></a>spawnvp

Имя функции, определяемой корпорацией Майкрософт `spawnvp`, является устаревшим псевдонимом для функции [_spawnvp](spawnvp-wspawnvp.md) . По умолчанию он создает [Предупреждение компилятора (уровень 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Имя является устаревшим, так как оно не соответствует стандартным правилам C для имен, зависящих от реализации. Однако функция по-прежнему поддерживается.

Вместо этого рекомендуется использовать [_spawnvp](spawnvp-wspawnvp.md) . Вы также можете продолжить использовать это имя функции и отключить предупреждение. Дополнительные сведения см. [в разделе Отключение](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) [имен функций](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names)Warning и POSIX.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).
