---
title: Неустранимая ошибка компилятора ресурсов RC1018 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC1018
dev_langs:
- C++
helpviewer_keywords:
- RC1018
ms.assetid: bb1d2efd-6898-412f-bb03-9ff94c54e4dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc54586d03aaf84882120cee0428990caa8cae97
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33339856"
---
# <a name="resource-compiler-fatal-error-rc1018"></a>Неустранимая ошибка компилятора ресурсов RC1018
Непредвиденный «#elif»  
  
 `#elif` Директива не отображается в `#if`, **#ifdef**, или **#ifndef** построения.  
  
 Убедитесь, что имеется `#if`, **#ifdef**, или **#ifndef** инструкции фактически перед этим оператором.