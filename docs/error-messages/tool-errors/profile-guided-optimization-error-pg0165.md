---
title: "Профильной оптимизации PG0165 ошибка | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PG0165
dev_langs: C++
helpviewer_keywords: PG0165
ms.assetid: e98122e7-ddee-4a2c-96b2-d232e4c65f3e
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 32b9f5f3ee335aac0a8382377aa850c3b91a27a0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="profile-guided-optimization-error-pg0165"></a>Ошибка профильной оптимизации PG0165
Чтение «Filename.pgd»: "версия PGD не поддерживается (несоответствие версии)".  
  
 Файлы PGD соответствуют определенному набору инструментов компилятора. Эта ошибка возникает при использовании компилятора, используемое для *Filename*.pgd. Эта ошибка указывает, что набор инструментов компилятора не может использовать данные из *Filename*.pgd для оптимизации текущей программы.  
  
 Чтобы устранить эту проблему, создайте заново *Filename*.pgd, используя текущий набор инструментов компилятора.