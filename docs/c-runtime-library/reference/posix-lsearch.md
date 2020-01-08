---
title: lsearch
ms.date: 12/16/2019
api_name:
- lsearch
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
- lsearch
helpviewer_keywords:
- lsearch function
ms.assetid: 130da3fc-904a-4375-b0ab-79bfea8a455f
ms.openlocfilehash: a068b6500de8a1a795f5494ac12afa0e5ca08544
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75300889"
---
# <a name="lsearch"></a>lsearch

Имя функции POSIX, реализуемой корпорацией Майкрософт `lsearch` является устаревшим псевдонимом для функции [_lsearch](lsearch.md) . По умолчанию он создает [Предупреждение компилятора (уровень 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Имя является устаревшим, так как оно не соответствует стандартным правилам C для имен, зависящих от реализации. Однако функция по-прежнему поддерживается.

Вместо этого рекомендуется использовать [_lsearch](lsearch.md) или расширенную безопасность [_lsearch_s](lsearch-s.md) функции. Вы также можете продолжить использовать это имя функции и отключить предупреждение. Дополнительные сведения см. [в разделе Отключение](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) [имен функций](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names)Warning и POSIX.
