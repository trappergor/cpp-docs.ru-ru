---
title: sopen
ms.date: 12/16/2019
api_name:
- sopen
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
- sopen
helpviewer_keywords:
- sopen function
ms.assetid: 1ce0b707-0c9e-4942-8467-ce7f6cd68acc
ms.openlocfilehash: 83ec3ee87f16d37d651b2e7a37e0f7eaebe0f46d
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75300720"
---
# <a name="sopen"></a>sopen

Имя функции, определяемой корпорацией Майкрософт `sopen`, является устаревшим псевдонимом для функции [_sopen](sopen-wsopen.md) . По умолчанию он создает [Предупреждение компилятора (уровень 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Имя является устаревшим, так как оно не соответствует стандартным правилам C для имен, зависящих от реализации. Однако функция по-прежнему поддерживается.

Вместо этого рекомендуется использовать [_sopen](sopen-wsopen.md) или функцию [_sopen_s](sopen-s-wsopen-s.md) с повышенным уровнем безопасности. Вы также можете продолжить использовать это имя функции и отключить предупреждение. Дополнительные сведения см. [в разделе Отключение](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) [имен функций](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names)Warning и POSIX.
