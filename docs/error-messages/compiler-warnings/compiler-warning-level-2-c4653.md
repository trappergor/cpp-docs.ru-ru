---
title: Предупреждение компилятора (уровень 2) C4653 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4653
dev_langs:
- C++
helpviewer_keywords:
- C4653
ms.assetid: 90ec3317-3d39-4b4c-bcd1-97e7c799e1b6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 376da24d4619eacc3e6b3defe8fdfc582800a898
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045982"
---
# <a name="compiler-warning-level-2-c4653"></a>Предупреждение компилятора (уровень 2) C4653

параметр компилятора «параметр» несовместим с предкомпилированным заголовком; текущий параметр командной строки пропускается

Параметр, заданный с использование предкомпилированных заголовков ([/Yu](../../build/reference/yu-use-precompiled-header-file.md)) параметр несовместим с параметрами, заданными во время создания предкомпилированного заголовка. Этой компиляции используется параметр, заданный при создании предкомпилированного заголовка.

Это предупреждение может возникнуть, если другое значение для параметре ([/Zp](../../build/reference/zp-struct-member-alignment.md)) был указан во время компиляции предкомпилированного заголовка.