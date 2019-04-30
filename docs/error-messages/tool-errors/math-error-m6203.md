---
title: Математическая ошибка M6203
ms.date: 11/04/2016
f1_keywords:
- M6203
helpviewer_keywords:
- M6203
ms.assetid: bd7fdd1c-83e4-4d6a-901e-10a0308bf5be
ms.openlocfilehash: 4433a024d461ee1bc43aa5fa82344190377243b4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400777"
---
# <a name="math-error-m6203"></a>Математическая ошибка M6203

«функция»: ошибка _OVERFLOW

Результат заданной функции слишком велико для представления.

Эта ошибка вызывает `_matherr` функцию с именем функции, аргументы и тип ошибки. Можно переписать `_matherr` функции для обработки определенных ошибок времени выполнения вычисления с плавающей запятой.