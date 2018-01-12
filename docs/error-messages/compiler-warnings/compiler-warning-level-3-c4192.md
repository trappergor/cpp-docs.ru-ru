---
title: "Предупреждение (уровень 3) C4192 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4192
dev_langs: C++
helpviewer_keywords: C4192
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 022c0e0aac8d231963ddf6d5d3715d55f726a8b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4192"></a>Предупреждение (уровень 3) C4192 компилятора
автоматически исключается 'name' при импорте библиотеки типов «библиотека»  
  
 Объект `#import` библиотека содержит элемент, *имя*, в котором также определены в системных заголовочных файлах Win32. Из-за ограничений библиотек типов, имена, такие как **IUnknown** или GUID часто определяются в библиотеках типов, дублирует определения системных заголовочных файлах. `#import`обнаружит эти элементы и не будет встраивать их в TLH-файлы и TLI-файлы.  
  
 Чтобы переопределить это поведение, используйте `#import` атрибуты [no_auto_exclude](../../preprocessor/no-auto-exclude.md) и [include()](../../preprocessor/include-parens.md).