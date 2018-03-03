---
title: "Неустранимая ошибка NMAKE U1059 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U1059
dev_langs:
- C++
helpviewer_keywords:
- U1059
ms.assetid: b21d9198-9c63-40d0-b589-80e17294ce24
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fb9ba98b0f82c158e4e11859e85af72efdbbc244
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1059"></a>Неустранимая ошибка NMAKE U1059
Синтаксическая ошибка: "}" отсутствует в зависимости  
  
 Неправильно указан путь поиска для зависимости. Существовали пробелы в пути или закрывающей фигурной скобкой (**}**) был пропущен.  
  
 Синтаксис спецификации директории для зависимости:  
  
 **{**   
 ***каталоги* } зависимые**  
  
 где `directories` указывает один или несколько путей, разделяя их точкой с запятой (**;**). Пробелы не допускаются.  
  
 Если макрос заменяется всех или части пути поиска, убедитесь, что в расширении макроса существуют без пробелов.