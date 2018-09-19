---
title: Ошибка компилятора C2667 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2667
dev_langs:
- C++
helpviewer_keywords:
- C2667
ms.assetid: 3c91d9d1-18fa-4e0d-a9ba-984d38980ca3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5d6d14cf04ae399b10cbaa393d9e9fcc7133f274
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095252"
---
# <a name="compiler-error-c2667"></a>Ошибка компилятора C2667

«функция»: ни одна из перегрузок нет наилучшего преобразования

Вызов перегруженной функции является неоднозначным и не может быть разрешен.

Преобразование, требуемое для соответствия фактических параметров в вызове функции к одному из перегруженных функций должно быть строго лучше, чем необходимо для всех перегруженных функций преобразования.

См. в статье базы знаний Q240869 подробнее на частичное Упорядочение шаблонов функций.