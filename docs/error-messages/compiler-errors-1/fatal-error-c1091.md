---
title: Неустранимая ошибка C1091 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1091
dev_langs:
- C++
helpviewer_keywords:
- C1091
ms.assetid: 812d4201-9154-48b0-b9af-5959c082ca33
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c48c9dca72bddc844e94fb7978cb6414aa8fecf5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33226226"
---
# <a name="fatal-error-c1091"></a>Неустранимая ошибка C1091
ограничение компилятора: длина строки превышает "длину" байт  
  
 Длина строковой константы превышает установленное ограничение.  
  
 Можно разбить статическую строку на две (или более) переменных и использовать функцию [strcpy_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) для объединения результатов в объявлении или во время выполнения.