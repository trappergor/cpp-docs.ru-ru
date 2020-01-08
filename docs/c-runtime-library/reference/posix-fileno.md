---
title: fileno
ms.date: 12/16/2019
api_name:
- fileno
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
- fileno
helpviewer_keywords:
- fileno function
ms.assetid: 8f33e1e0-0dc8-4311-b690-ec6e577a64b5
ms.openlocfilehash: 798334e4139209be50c665d112f502f60909ed0f
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301175"
---
# <a name="fileno"></a>fileno

Имя функции POSIX, реализуемой корпорацией Майкрософт `fileno` является устаревшим псевдонимом для функции [_fileno](fileno.md) . По умолчанию он создает [Предупреждение компилятора (уровень 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Имя является устаревшим, так как оно не соответствует стандартным правилам C для имен, зависящих от реализации. Однако функция по-прежнему поддерживается.

Вместо этого рекомендуется использовать [_fileno](fileno.md) . Вы также можете продолжить использовать это имя функции и отключить предупреждение. Дополнительные сведения см. [в разделе Отключение](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) [имен функций](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names)Warning и POSIX.
