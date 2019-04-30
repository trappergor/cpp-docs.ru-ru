---
title: Предупреждение компилятора (уровень 1) C4420
ms.date: 11/04/2016
f1_keywords:
- C4420
helpviewer_keywords:
- C4420
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
ms.openlocfilehash: a4a7e91e7845cc0fc25d5a6fad16ae7b7e327952
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408177"
---
# <a name="compiler-warning-level-1-c4420"></a>Предупреждение компилятора (уровень 1) C4420

«operator»: оператор недоступен, вместо этого «operator»; проверки времени выполнения могут быть скомпрометированы

Это предупреждение создается при использовании [правильной/RTCv](../../build/reference/rtc-run-time-error-checks.md) (vector проверка) и при обнаружении не векторную форму. В этом случае используется не векторную форму.

Для правильной работы правильно/RTCv, компилятор должен всегда вызывать векторную форму [новый](../../cpp/new-operator-cpp.md)/[удалить](../../cpp/delete-operator-cpp.md) Если использовался синтаксис вектор.