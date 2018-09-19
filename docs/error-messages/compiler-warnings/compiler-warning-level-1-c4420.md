---
title: Предупреждение компилятора (уровень 1) C4420 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4420
dev_langs:
- C++
helpviewer_keywords:
- C4420
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1ba4ef4c4fc006e1a5950d0d16dc530ccc06a1d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049752"
---
# <a name="compiler-warning-level-1-c4420"></a>Предупреждение компилятора (уровень 1) C4420

«operator»: оператор недоступен, вместо этого «operator»; проверки времени выполнения могут быть скомпрометированы

Это предупреждение создается при использовании [правильной/RTCv](../../build/reference/rtc-run-time-error-checks.md) (vector проверка) и при обнаружении не векторную форму. В этом случае используется не векторную форму.

Для правильной работы правильно/RTCv, компилятор должен всегда вызывать векторную форму [новый](../../cpp/new-operator-cpp.md)/[удалить](../../cpp/delete-operator-cpp.md) Если использовался синтаксис вектор.