---
title: Предупреждение компилятора (уровень 1) C4025 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4025
dev_langs:
- C++
helpviewer_keywords:
- C4025
ms.assetid: c4f6a651-0641-4446-973e-8290065e49ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 109f1694f63488c167e51c7c2c89675411b6d269
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045579"
---
# <a name="compiler-warning-level-1-c4025"></a>Предупреждение компилятора (уровень 1) C4025

"число": относительный указатель передан в функцию с аргументами-переменными: параметр <номер>

Передача относительного указателя в функцию с аргументами-переменными нормализует указатель с непредвиденными результатами. Не передавайте относительные указатели в функции с аргументами-переменными.