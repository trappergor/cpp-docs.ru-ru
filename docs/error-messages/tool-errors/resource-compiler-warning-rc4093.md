---
title: Предупреждение компилятора ресурсов RC4093 | Документы Microsoft
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
ms.openlocfilehash: e9cca3c2a139e1109746f3a690cfb3f31509a9fe
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322436"
---
# <a name="resource-compiler-warning-rc4093"></a>Предупреждение компилятора ресурсов RC4093
escape-последовательность новой строки в символьной константе в неактивного кода  
  
 Константное выражение `#if`, `#elif`, **#ifdef**, или **#ifndef** директивы препроцессора, равно нулю, что делает код, который следует за неактивным. Внутри этого неактивного кода знак новой строки заключен в одинарные или двойные кавычки.  
  
 Весь текст до следующих двойных кавычек рассматривается как внутри символьной константы.