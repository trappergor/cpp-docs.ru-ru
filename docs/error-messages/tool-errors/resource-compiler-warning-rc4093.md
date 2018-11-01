---
title: Предупреждение компилятора ресурсов RC4093
ms.date: 11/04/2016
f1_keywords:
- RC4093
helpviewer_keywords:
- RC4093
ms.assetid: 3c61b4a4-b418-465b-a4fd-cb1ff0adb8dd
ms.openlocfilehash: 23bf436e6e8338f89bc576564181c84715028332
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50541886"
---
# <a name="resource-compiler-warning-rc4093"></a>Предупреждение компилятора ресурсов RC4093

escape-последовательность новой строки в символьной константы в неактивный код

Константное выражение `#if`, `#elif`, **#ifdef**, или **#ifndef** директива препроцессора, равно нулю, что делает код, который следует за неактивные. Внутри этого неактивного кода символ заключен в одинарные или двойные кавычки.

Считается, что весь текст до следующего двойная кавычка была внутри символьной константы.