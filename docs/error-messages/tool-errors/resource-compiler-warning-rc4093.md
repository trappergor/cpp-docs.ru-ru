---
title: Предупреждение компилятора ресурсов RC4093
ms.date: 11/04/2016
f1_keywords:
- RC4093
helpviewer_keywords:
- RC4093
ms.assetid: 3c61b4a4-b418-465b-a4fd-cb1ff0adb8dd
ms.openlocfilehash: 29d24f1e380f5c531e170e5dc23cf5c77eefb874
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182296"
---
# <a name="resource-compiler-warning-rc4093"></a>Предупреждение компилятора ресурсов RC4093

неэкранированная новая строка в символьной константе в неактивном коде

Константное выражение `#if`, `#elif`, **#ifdef**или **#ifndef** директивы препроцессора вычислено до нуля, делая код неактивным. Внутри этого неактивного кода символ новой строки присутствует в наборе одинарных или двойных кавычек.

Весь текст, пока следующая двойная кавычка не считается в символьной константе.
