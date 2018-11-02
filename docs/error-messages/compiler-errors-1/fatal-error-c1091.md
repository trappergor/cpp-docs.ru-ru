---
title: Неустранимая ошибка C1091
ms.date: 11/04/2016
f1_keywords:
- C1091
helpviewer_keywords:
- C1091
ms.assetid: 812d4201-9154-48b0-b9af-5959c082ca33
ms.openlocfilehash: 9758d4b779f4727012041da60632bcea8ce18d42
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624969"
---
# <a name="fatal-error-c1091"></a>Неустранимая ошибка C1091

ограничение компилятора: длина строки превышает "длину" байт

Длина строковой константы превышает установленное ограничение.

Можно разбить статическую строку на две (или более) переменных и использовать функцию [strcpy_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) для объединения результатов в объявлении или во время выполнения.