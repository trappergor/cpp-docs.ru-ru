---
title: Предупреждение компилятора (уровень 1) C4799 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4799
dev_langs:
- C++
helpviewer_keywords:
- C4799
ms.assetid: 8ecbd06f-c778-4371-a2fb-c690b6743ec8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b3d83917289e5ad76a874587894a66e163fed90a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088232"
---
# <a name="compiler-warning-level-1-c4799"></a>Предупреждение компилятора (уровень 1) C4799

> Нет EMMS в конце функции "*функция*"

Функция имеет по крайней мере одной инструкции MMX, но не имеет `EMMS` инструкции. При использовании мультимедийной инструкции `EMMS` инструкции или `_mm_empty` внутренние также следует использовать для очистки мультимедийного тега слово в конце кода MMX.

Вы можете получить C4799, когда с помощью файла, указывающее, что код не использует правильно выполнять инструкции EMMS перед возвратом. Это значение false, предупреждения для этих заголовков. Можно отключить их, определив _SILENCE_IVEC_C4799 в файла. Однако имейте в виду, что это будет также запретить компилятору верные предупреждения этого типа.

Дополнительные сведения см. в разделе [набор инструкций MMX Intel](../../assembler/inline/intel-s-mmx-instruction-set.md).