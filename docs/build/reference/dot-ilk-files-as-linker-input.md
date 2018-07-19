---
title: . Компоновщик-ввод ILK-файлы | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ILK files
- .ilk files
ms.assetid: 7324c104-9e5d-423d-b268-b59f92607bf2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01fea585b86114373017b6d73948cb1438b7185e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371688"
---
# <a name="ilk-files-as-linker-input"></a>ILK-файлы в качестве входных файлов компоновщика
При связывании постепенно, LINK обновляет состояние ILK-файл, созданный во время первого инкрементной компоновки. Этот файл имеет такое же базовое имя файла .exe или DLL-файл, и имеет расширение .ilk. При выполнении последующих LINK обновляет ILK-файл. Если отсутствует ILK-файл, LINK выполняет полною компоновку и создает новый ILK-файл. Если ILK-файл не может использоваться, LINK выполняет компоновку недобавочная. Дополнительные сведения об инкрементной компоновке см. в разделе [постепенно связи (/ INCREMENTAL)](../../build/reference/incremental-link-incrementally.md) параметр.  
  
## <a name="see-also"></a>См. также  
 [Входные LINK-файлы](../../build/reference/link-input-files.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)