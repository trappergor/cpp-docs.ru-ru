---
title: Предупреждение BSCMAKE BK4504 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK4504
dev_langs:
- C++
helpviewer_keywords:
- BK4504
ms.assetid: b56ee2d4-ad44-40f4-98c0-75934ea44a6c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5a17aa8b4e2a98d3bda5d21ea84962791b8051dc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="bscmake-warning-bk4504"></a>Предупреждение BSCMAKE BK4504
файл содержит слишком много ссылок; Пропуск дальнейшие ссылки из этого источника  
  
 В CPP-файл содержит более 64 000 ссылок на символы. BSCMAKE обнаружил 64 000 ссылки в файле, пропускает все дальнейшие ссылки.  
  
 Чтобы устранить проблему, либо разбит на два файла или нескольких файлов, каждый из которых имеет не более 64 000 ссылок на символы, либо используйте `#pragma component(browser)` директива препроцессора, ограничение символы, которые создаются для определенного ссылки. Дополнительные сведения см. в разделе [компонента](../../preprocessor/component.md).