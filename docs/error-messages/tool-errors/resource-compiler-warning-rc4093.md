---
title: "Предупреждение компилятора ресурсов RC4093 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RC4093
dev_langs: C++
helpviewer_keywords: RC4093
ms.assetid: 3c61b4a4-b418-465b-a4fd-cb1ff0adb8dd
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4d21cbba379e72675b8957be58dc712b83673947
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-warning-rc4093"></a>Предупреждение компилятора ресурсов RC4093
escape-последовательность новой строки в символьной константе в неактивного кода  
  
 Константное выражение `#if`, `#elif`, **#ifdef**, или **#ifndef** директивы препроцессора, равно нулю, что делает код, который следует за неактивным. Внутри этого неактивного кода знак новой строки заключен в одинарные или двойные кавычки.  
  
 Весь текст до следующих двойных кавычек рассматривается как внутри символьной константы.