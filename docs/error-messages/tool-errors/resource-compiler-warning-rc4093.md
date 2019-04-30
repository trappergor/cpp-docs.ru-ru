---
title: Предупреждение компилятора ресурсов RC4093
ms.date: 11/04/2016
f1_keywords:
- RC4093
helpviewer_keywords:
- RC4093
ms.assetid: 3c61b4a4-b418-465b-a4fd-cb1ff0adb8dd
ms.openlocfilehash: 23bf436e6e8338f89bc576564181c84715028332
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62346214"
---
# <a name="resource-compiler-warning-rc4093"></a>Предупреждение компилятора ресурсов RC4093

escape-последовательность новой строки в символьной константы в неактивный код

Константное выражение `#if`, `#elif`, **#ifdef**, или **#ifndef** директива препроцессора, равно нулю, что делает код, который следует за неактивные. Внутри этого неактивного кода символ заключен в одинарные или двойные кавычки.

Считается, что весь текст до следующего двойная кавычка была внутри символьной константы.