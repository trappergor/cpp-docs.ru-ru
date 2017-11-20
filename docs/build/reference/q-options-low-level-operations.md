---
title: "Параметры -Q (низкоуровневые операции) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /q
dev_langs: C++
helpviewer_keywords:
- Q compiler option [C++]
- -Q compiler option [C++]
- /Q compiler option [C++]
ms.assetid: 9fa738b9-630a-4bde-bc87-bdfa30552be4
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0fb7ef41e40b2ce6f4b3555de5b2369cc2d7a460
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="q-options-low-level-operations"></a>Параметры /Q (низкоуровневые операции)
Можно использовать **/q** параметры компилятора для выполнения следующих операций компилятора низкого уровня:  
  
-   [/ Qfast_transcendentals (принудительное использование быстрых трансцендентных функций)](../../build/reference/qfast-transcendentals-force-fast-transcendentals.md): создает быстрые трансцендентные функции.  
  
-   [/ QIfist (отключение _ftol)](../../build/reference/qifist-suppress-ftol.md): подавляет `_ftol` при необходимости преобразования из типа с плавающей запятой в целочисленный тип является обязательным (x86 только).  
  
-   [/ Qimprecise_fwaits (удалить ожидания в блоке Try)](../../build/reference/qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): Удаляет `fwait` команды внутрь `try` блоков.  
  
-   [/ Qpar (автоматический Параллелизатор)](../../build/reference/qpar-auto-parallelizer.md): включает автоматическую параллелизацию циклов, которые отмечены [#pragma loop()](../../preprocessor/loop.md) директивы.  
  
-   [/ Qpar-report (уровень отчетности автоматического Параллелизатора)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md): включает уровни отчетов для автоматической параллелизации.  
  
-   [/ Qsafe_fp_loads](../../build/reference/qsafe-fp-loads.md): подавляет оптимизацию для регистре с плавающей запятой, загружает и перемещение между памяти и MMX регистры.  
  
-   [/ Qvec-report (уровень отчетности автоматического Векторизатора)](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md): включает уровни отчетов для автоматической векторизации.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)