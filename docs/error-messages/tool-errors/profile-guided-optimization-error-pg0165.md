---
title: Профильной оптимизации PG0165 ошибка | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PG0165
dev_langs:
- C++
helpviewer_keywords:
- PG0165
ms.assetid: e98122e7-ddee-4a2c-96b2-d232e4c65f3e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: acad97411480112d06dadd454d1368dcfdf2c87f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="profile-guided-optimization-error-pg0165"></a>Ошибка профильной оптимизации PG0165
Чтение «Filename.pgd»: "версия PGD не поддерживается (несоответствие версии)".  
  
 Файлы PGD соответствуют определенному набору инструментов компилятора. Эта ошибка возникает при использовании компилятора, используемое для *Filename*.pgd. Эта ошибка указывает, что набор инструментов компилятора не может использовать данные из *Filename*.pgd для оптимизации текущей программы.  
  
 Чтобы устранить эту проблему, создайте заново *Filename*.pgd, используя текущий набор инструментов компилятора.