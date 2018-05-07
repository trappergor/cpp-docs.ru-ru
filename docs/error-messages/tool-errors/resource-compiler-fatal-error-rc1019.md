---
title: Неустранимая ошибка компилятора ресурсов RC1019 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC1019
dev_langs:
- C++
helpviewer_keywords:
- RC1019
ms.assetid: 432fff44-04a9-4e13-91c6-870df6f0b4e4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1cd9658a97f1f62a2a5a262e7262127744dd144a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="resource-compiler-fatal-error-rc1019"></a>Неустранимая ошибка компилятора ресурсов RC1019
Непредвиденная "#else"  
  
 `#else` Директива не отображается в `#if`, **#ifdef**, или **#ifndef** построения.  
  
 Убедитесь, что имеется `#if`, **#ifdef**, или **#ifndef** инструкции фактически перед этим оператором.