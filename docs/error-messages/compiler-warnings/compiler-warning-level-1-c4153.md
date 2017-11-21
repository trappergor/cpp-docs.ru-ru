---
title: "Предупреждение (уровень 1) C4153 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4153
dev_langs: C++
helpviewer_keywords: C4153
ms.assetid: 37a15754-9dba-470b-adda-c4b888064b3e
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c46774d944e6a7187a4345f76e1f8e7c7e7c3f87
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4153"></a>Предупреждение компилятора (уровень 1) C4153
преобразование указателя на функцию в указатель на данные (или наоборот) в выражении  
  
 Указатель на функцию преобразуется в указатель на данные или наоборот. Подобное преобразование допустимо при использовании расширений Майкрософт (/Ze), но не в ANSI C.