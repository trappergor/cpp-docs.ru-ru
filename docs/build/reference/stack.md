---
title: -STACK | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /stack
dev_langs:
- C++
helpviewer_keywords:
- -STACK editbin option
- STACK editbin option
- stack, setting size
- /STACK editbin option
ms.assetid: a39bcff0-c945-4355-80cc-8e4f24a5f142
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a82111ce950d14bc6b3e270ee9a658d806b28b62
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374080"
---
# <a name="stack"></a>/STACK
```  
/STACK:reserve[,commit]  
```  
  
## <a name="remarks"></a>Примечания  
 Этот параметр задает размер стека в байтах и принимает аргументы в десятичной нотации или языка C нотации. Параметр/Stack применяется только к исполняемым файлом.  
  
 *Зарезервировать* аргумент задает все выделение стека в виртуальной памяти. EDITBIN округляет указанное значение до ближайших 4 байт.  
  
 Необязательный `commit` аргумент интерпретируется операционной системой. В Windows NT, Windows 95 и Windows 98 `commit` указывает объем физической памяти для выделения одновременно. Выделенная виртуальная память резервирует пространство в файле подкачки. Более высокий `commit` значение экономит время, когда приложению требуется больший объем стека, однако увеличивает требования к памяти и, возможно, время запуска.  
  
## <a name="see-also"></a>См. также  
 [Параметры EDITBIN](../../build/reference/editbin-options.md)