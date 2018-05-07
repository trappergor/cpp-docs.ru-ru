---
title: -TLS | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /TLS
dev_langs:
- C++
helpviewer_keywords:
- /TLS dumpbin option
- -TLS dumpbin option
ms.assetid: 2b3f48f9-cac4-4351-b15c-2833b43bc709
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b5e510f406ceae7508f9b84f99e7ab397d22f114
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="tls"></a>/TLS
Отображает структуру IMAGE_TLS_DIRECTORY из исполняемого файла.  
  
## <a name="remarks"></a>Примечания  
 / TLS отображает поля структуры TLS и адреса функций обратного вызова TLS.  
  
 Если программа использует локальное хранилище потока, ее изображение не будет содержать структуру TLS.  В разделе [поток](../../cpp/thread.md) для получения дополнительной информации.  
  
 IMAGE_TLS_DIRECTORY, определенный в заголовке winnt.h.  
  
## <a name="see-also"></a>См. также  
 [Параметры DUMPBIN](../../build/reference/dumpbin-options.md)