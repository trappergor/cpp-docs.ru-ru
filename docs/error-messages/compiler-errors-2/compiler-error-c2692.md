---
title: Ошибка компилятора C2692
ms.date: 11/04/2016
f1_keywords:
- C2692
helpviewer_keywords:
- C2692
ms.assetid: 02ade3b4-b757-448b-b065-d7d71bc3f441
ms.openlocfilehash: c469f4944417c9116c7316b01642dd4b370b8c4b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50611163"
---
# <a name="compiler-error-c2692"></a>Ошибка компилятора C2692

«имя функции»: полным прототипом функции, необходимые в компиляторе C с "/ clr" параметр

При компиляции для .NET, управляемый код, компилятор C требует объявления функций ANSI. Кроме того, если функция не принимает параметров, его необходимо явно объявить `void` тип параметра.