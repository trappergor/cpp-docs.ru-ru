---
title: Ошибка компилятора C2692
ms.date: 11/04/2016
f1_keywords:
- C2692
helpviewer_keywords:
- C2692
ms.assetid: 02ade3b4-b757-448b-b065-d7d71bc3f441
ms.openlocfilehash: c469f4944417c9116c7316b01642dd4b370b8c4b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257820"
---
# <a name="compiler-error-c2692"></a>Ошибка компилятора C2692

«имя функции»: полным прототипом функции, необходимые в компиляторе C с "/ clr" параметр

При компиляции для .NET, управляемый код, компилятор C требует объявления функций ANSI. Кроме того, если функция не принимает параметров, его необходимо явно объявить `void` тип параметра.