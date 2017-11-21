---
title: "Предупреждение BSCMAKE BK4504 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: BK4504
dev_langs: C++
helpviewer_keywords: BK4504
ms.assetid: b56ee2d4-ad44-40f4-98c0-75934ea44a6c
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f7f6d854fbd74d9ca05ba6797bbd57db52b7a70e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="bscmake-warning-bk4504"></a>Предупреждение BSCMAKE BK4504
файл содержит слишком много ссылок; Пропуск дальнейшие ссылки из этого источника  
  
 В CPP-файл содержит более 64 000 ссылок на символы. BSCMAKE обнаружил 64 000 ссылки в файле, пропускает все дальнейшие ссылки.  
  
 Чтобы устранить проблему, либо разбит на два файла или нескольких файлов, каждый из которых имеет не более 64 000 ссылок на символы, либо используйте `#pragma component(browser)` директива препроцессора, ограничение символы, которые создаются для определенного ссылки. Дополнительные сведения см. в разделе [компонента](../../preprocessor/component.md).