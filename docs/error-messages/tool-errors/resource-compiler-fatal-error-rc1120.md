---
title: Неустранимая ошибка компилятора ресурсов RC1120 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC1120
dev_langs:
- C++
helpviewer_keywords:
- RC1120
ms.assetid: 4e462931-e42e-42e3-8bfc-847677194286
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d117f7b106e14cde2def5477fab5ad0fc92a6411
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="resource-compiler-fatal-error-rc1120"></a>Неустранимая ошибка компилятора ресурсов RC1120
не хватает памяти необходимо количество байтов  
  
 Компилятору ресурсов не хватило места для хранения элементов, которые в нем хранятся в его куче. Обычно это результат использования слишком много символов.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки  
  
1.  Увеличьте размер файла подкачки Windows. См. Дополнительные сведения об увеличении размер файла подкачки виртуальной памяти в справочной системе Windows.  
  
2.  Удалите неиспользуемые включаемые файлы, особенно ненужные `#define`и прототипы функций.  
  
3.  Разделите данный файл на два или более файлов и компилировать их по отдельности.  
  
4.  Удалите другие программы или драйверы, запущенные в системе, которая может расходоваться значительный объем памяти.