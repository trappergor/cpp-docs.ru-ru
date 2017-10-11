---
title: "Неустранимая ошибка C1905 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1905
dev_langs:
- C++
helpviewer_keywords:
- C1905
ms.assetid: fefc6769-477f-45a2-9878-6f0a5f42472c
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 9d1662b05764500d0ac6a96119f865294cac260b
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="fatal-error-c1905"></a>Неустранимая ошибка C1905
Внешний и внутренний сегменты несовместимы (должны быть предназначены для одного и того же процессора)  
  
 Эта ошибка возникает, когда OBJ-файл создан внешним сегментом компилятора (C1.dll), предназначенного для одного процессора, например, x86, ARM или [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], но этот файл считывается внутренним сегментом (C2.dll), предназначенным для другого процессора.  
  
 Чтобы устранить эту проблему убедитесь, что вы используете совпадающие внутренний и внешний сегменты. Такая конфигурация используется по умолчанию для проектов, создаваемых в Visual Studio. Эта ошибка может возникнуть, если вы отредактировали файл проекта и использовали другие пути к средствам компилятора. Если вы не задали явным образом путь к средствам компилятора, то эта ошибка может возникнуть при повреждении установки Visual Studio. Например, вы могли скопировать DLL-файлы компилятора из одного места в другое. Используйте **программы и компоненты** панели управления Windows для восстановления или переустановки Visual Studio.
