---
title: "Ошибка построения проекта PRJ0024 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- PRJ0024
dev_langs:
- C++
helpviewer_keywords:
- PRJ0024
ms.assetid: 8bde6368-6c1b-4e04-bc5e-3c6d0b8fa1d7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2cf9ad974856f132599932a32b954e50453adf56
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0024"></a>Ошибка построения проекта PRJ0024
Юникод-путь «path» не может быть преобразована в кодовую страницу ANSI пользователя.  
  
 ***путь*** — исходная версия строки пути в Юникоде. Эта ошибка может произойти в случаях, где имеется путь в формате Юникод, нельзя напрямую преобразовать в формат ANSI для текущей кодовой страницы системы.  
  
 Эта ошибка может возникать при работе с проектом, который был разработан в системе с использованием кодовой страницы, которая не находится на компьютере.  
  
 Способ устранения этой ошибки является обновление путь для использования текст ANSI или установите кодовую страницу на компьютере и определен как системный объект по умолчанию.