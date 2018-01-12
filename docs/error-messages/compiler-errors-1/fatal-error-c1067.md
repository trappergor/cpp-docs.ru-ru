---
title: "Неустранимая ошибка C1067 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1067
dev_langs: C++
helpviewer_keywords: C1067
ms.assetid: e2c94be6-4573-4571-aac9-73d657fe9f96
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8889ccbfcac31917948da719444dab68a2d1b9c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1067"></a>Неустранимая ошибка C1067
ограничение компилятора: превышен предельный размер записи типа 64 КБ  
  
 Эта ошибка может возникать, если символ имеет внутреннее имя, длина которых превышает 247 символов.  Чтобы решить, сократите имя символа.  
  
 Когда компилятор создает отладочную информацию, он создает записи типа, чтобы определить типы, встречающиеся в исходном коде.  Например записи типа могут включать простые структуры и списки аргументов функций.  Некоторые из этих записей типа может быть большие списки.  
  
 Ограничено 64 КБ на размер записи любого типа.  При превышении этого предела 64 КБ, возникнет эта ошибка.  
  
 C1067 также может возникать, если количеством символов с длинными именами или если класс, структура или объединение содержит слишком много членов.