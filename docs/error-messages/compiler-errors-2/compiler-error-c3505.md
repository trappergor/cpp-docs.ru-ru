---
title: Ошибка компилятора C3505 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3505
dev_langs:
- C++
helpviewer_keywords:
- C3505
ms.assetid: ed73c99e-93a1-4f3a-bac7-ba7ed5d836e4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0d6af1b96f23332b5eed82fab2c24c93e2d53dee
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054978"
---
# <a name="compiler-error-c3505"></a>Ошибка компилятора C3505

> не удается загрузить библиотеку типов "*guid*"

C3505 может возникать, если вы используете 32-разрядной, размещенный в x86 кросс компилятор для 64-разрядных систем, x64 целевых объектов на 64-разрядной платформе компьютера, так как компилятор работает в режиме WOW64 и можно только считывать из 32-разрядном кусте реестра.

Можно устранить эту ошибку, создав 32-разрядных и 64-разрядные версии библиотеки типов, который вы пытаетесь импортировать и затем зарегистрировать их обоих.  Или можно использовать собственный 64-разрядный компилятор, который требует изменить ваш **каталоги VC ++** свойство в интегрированной среде разработки, чтобы он указывал на 64-разрядный компилятор.

Дополнительные сведения см. в следующих разделах:

- [Практическое руководство. Использование набора 64-разрядных инструментов Visual C++ в командной строке](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)

- [Практическое руководство. Настройка проектов Visual C++ для 64-разрядных платформ с архитектурой x64](../../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md)