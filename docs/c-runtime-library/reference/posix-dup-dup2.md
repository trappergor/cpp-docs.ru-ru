---
title: dup, dup2
ms.date: 12/16/2019
api_name:
- dup2
- dup
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
- dup
- dup2
helpviewer_keywords:
- dup function
- dup2 function
ms.assetid: c7572170-47ff-4e0d-b9c3-10f0ab0ba40a
ms.openlocfilehash: ea6fe475b4a5e3cce5e9d05d89bd351361c2a4de
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301214"
---
# <a name="dup-dup2"></a>dup, dup2

Имена функций POSIX, реализованные корпорацией Майкрософт `dup` и `dup2`, являются устаревшими псевдонимами для функций [_dup](dup-dup2.md) и [_dup2](dup-dup2.md) . По умолчанию они генерируют [Предупреждение компилятора (уровень 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Имена являются устаревшими, так как они не соответствуют стандартным правилам C для имен, зависящих от реализации. Однако функции по-прежнему поддерживаются.

Вместо этого рекомендуется использовать [_dup](dup-dup2.md) и [_dup2](dup-dup2.md) . Вы также можете продолжать использовать эти имена функций и отключить предупреждение. Дополнительные сведения см. [в разделе Отключение](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) [имен функций](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names)Warning и POSIX.
