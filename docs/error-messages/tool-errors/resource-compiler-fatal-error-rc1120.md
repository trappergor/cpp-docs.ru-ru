---
title: "Неустранимая ошибка компилятора ресурсов RC1120 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RC1120
dev_langs: C++
helpviewer_keywords: RC1120
ms.assetid: 4e462931-e42e-42e3-8bfc-847677194286
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 28a35cc2f932cdf655324d05c10bdb875aa895a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-fatal-error-rc1120"></a>Неустранимая ошибка компилятора ресурсов RC1120
не хватает памяти необходимо количество байтов  
  
 Компилятору ресурсов не хватило места для хранения элементов, которые в нем хранятся в его куче. Обычно это результат использования слишком много символов.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки  
  
1.  Увеличьте размер файла подкачки Windows. См. Дополнительные сведения об увеличении размер файла подкачки виртуальной памяти в справочной системе Windows.  
  
2.  Удалите неиспользуемые включаемые файлы, особенно ненужные `#define`и прототипы функций.  
  
3.  Разделите данный файл на два или более файлов и компилировать их по отдельности.  
  
4.  Удалите другие программы или драйверы, запущенные в системе, которая может расходоваться значительный объем памяти.