---
title: Предупреждение компилятора ресурсов RC4093 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC4093
dev_langs:
- C++
helpviewer_keywords:
- RC4093
ms.assetid: 3c61b4a4-b418-465b-a4fd-cb1ff0adb8dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9b1ca04b17ebdb9d48bc94032482caf48ad4aa00
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111567"
---
# <a name="resource-compiler-warning-rc4093"></a>Предупреждение компилятора ресурсов RC4093

escape-последовательность новой строки в символьной константы в неактивный код

Константное выражение `#if`, `#elif`, **#ifdef**, или **#ifndef** директива препроцессора, равно нулю, что делает код, который следует за неактивные. Внутри этого неактивного кода символ заключен в одинарные или двойные кавычки.

Считается, что весь текст до следующего двойная кавычка была внутри символьной константы.