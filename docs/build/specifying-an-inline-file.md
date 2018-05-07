---
title: Указание встроенного файла | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, inline files
- inline files [C++], specifying NMAKE
- files [C++], inline
ms.assetid: 393eccfb-3fc9-4bac-a30c-8ac8d221cca3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2c0d85436aef5ed48c0a8787f8bce330bf6d3e96
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="specifying-an-inline-file"></a>Указание встроенного файла
Укажите две угловые скобки (<<) в команде где *filename* должна отображаться. Угловые скобки не может быть расширения макроса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
<<[filename]  
```  
  
## <a name="remarks"></a>Примечания  
 При выполнении команды угловые скобки заменяются *filename*, если указан или посредством уникального имени создается NMAKE. Если указано, *filename* должно следовать за угловыми скобками без пробел или символ табуляции. Допускается указание пути. Расширение не является необходимым Если *filename* указан, файл создается в текущем или указанном каталоге перезапись существующих файлов с тем же именем; в противном случае он создан в каталоге TMP (или текущем каталоге, если переменная среды TMP не определен). Если предыдущий *filename* — повторно, NMAKE заменяет предыдущий файл.  
  
## <a name="see-also"></a>См. также  
 [Подставляемые файлы в Makefile](../build/inline-files-in-a-makefile.md)