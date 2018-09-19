---
title: Ошибка компилятора C2692 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2692
dev_langs:
- C++
helpviewer_keywords:
- C2692
ms.assetid: 02ade3b4-b757-448b-b065-d7d71bc3f441
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 03a9006889c5853e77b5603484ea9d18f2474241
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088375"
---
# <a name="compiler-error-c2692"></a>Ошибка компилятора C2692

«имя функции»: полным прототипом функции, необходимые в компиляторе C с "/ clr" параметр

При компиляции для .NET, управляемый код, компилятор C требует объявления функций ANSI. Кроме того, если функция не принимает параметров, его необходимо явно объявить `void` тип параметра.