---
title: Оптимизация встроенного кода на языке ассемблера
ms.date: 08/30/2018
helpviewer_keywords:
- storage, optimizing in inline assembly
- optimization, inline assembly
- inline assembly, optimizing
- optimizing performance, inline assembly
- __asm keyword [C++], optimizing
ms.assetid: 52a7ec83-9782-4d96-94c1-53bb2ac9e8c8
ms.openlocfilehash: a558761ff49c2b508a5bad6172cda2283801e30e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87191733"
---
# <a name="optimizing-inline-assembly"></a>Оптимизация встроенного кода на языке ассемблера

**Блок, относящийся только к системам Microsoft**

Наличие **`__asm`** блока в функции влияет на оптимизацию несколькими способами. Во первых, компилятор не пытается оптимизировать **`__asm`** сам блок. То, что написано на языке ассемблера, то и получается. Во вторых, присутствие **`__asm`** блока влияет на регистрацию переменного хранилища. Компилятор позволяет избежать регистрирует переменных в **`__asm`** блоке, если содержимое регистра будет изменено **`__asm`** блоком. Наконец, включение языка ассемблера в функцию затрагивает некоторые другие аспекты оптимизации уровня функции.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенный ассемблер](../../assembler/inline/inline-assembler.md)<br/>
