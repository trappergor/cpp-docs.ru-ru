---
title: . Компоновщик-ввод ILK-файлы | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ILK files
- .ilk files
ms.assetid: 7324c104-9e5d-423d-b268-b59f92607bf2
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1b91d229e1c607be1ed35685ab7bfdffe2271e16
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ilk-files-as-linker-input"></a>ILK-файлы в качестве входных файлов компоновщика
При связывании постепенно, LINK обновляет состояние ILK-файл, созданный во время первого инкрементной компоновки. Этот файл имеет такое же базовое имя файла .exe или DLL-файл, и имеет расширение .ilk. При выполнении последующих LINK обновляет ILK-файл. Если отсутствует ILK-файл, LINK выполняет полною компоновку и создает новый ILK-файл. Если ILK-файл не может использоваться, LINK выполняет компоновку недобавочная. Дополнительные сведения об инкрементной компоновке см. в разделе [постепенно связи (/ INCREMENTAL)](../../build/reference/incremental-link-incrementally.md) параметр.  
  
## <a name="see-also"></a>См. также  
 [Входные LINK-файлы](../../build/reference/link-input-files.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)