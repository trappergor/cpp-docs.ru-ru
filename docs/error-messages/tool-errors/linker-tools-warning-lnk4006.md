---
title: "Предупреждение средств компоновщика LNK4006 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4006
dev_langs: C++
helpviewer_keywords: LNK4006
ms.assetid: 3a637d17-1676-4ea6-bd8b-290137d28d3b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 021961029d274172119ae92aa10cc6a236dd973b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4006"></a>Предупреждение средств компоновщика LNK4006
символ уже определен в объекте; Второе определение пропущено  
  
 Указанный символ `symbol`, отображаемый в декорированном виде, был определен несколько раз. При появлении этого предупреждения `symbol` будет добавлен дважды, но будет использоваться только первая его форма.  
  
 Это предупреждение может возникать при попытке объединения двух библиотек импорта в одну.  
  
 Если выполняется перестроение библиотеки времени выполнения C, это сообщение можно проигнорировать.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки  
  
1.  Данный `symbol` может быть упакованной функцией, созданной при компиляции с параметром [/Gy](../../build/reference/gy-enable-function-level-linking.md). Этот символ был включен в несколько файлов, но изменен в промежутке между компиляциями. Перекомпилируйте все файлы, включающие `symbol`.  
  
2.  Данный `symbol` мог быть определен по-разному в двух объектах-членах в различных библиотеках.  
  
3.  Является абсолютным могли быть определены дважды, с другим значением каждого определения.  
  
4.  Если получено сообщение об ошибке при комбинировании библиотек, `symbol` уже существует в библиотеке, добавляемый.