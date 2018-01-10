---
title: "-TLS | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /TLS
dev_langs: C++
helpviewer_keywords:
- /TLS dumpbin option
- -TLS dumpbin option
ms.assetid: 2b3f48f9-cac4-4351-b15c-2833b43bc709
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5adf246e343a16abebdc584589e9633b195444ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="tls"></a>/TLS
Отображает структуру IMAGE_TLS_DIRECTORY из исполняемого файла.  
  
## <a name="remarks"></a>Примечания  
 / TLS отображает поля структуры TLS и адреса функций обратного вызова TLS.  
  
 Если программа использует локальное хранилище потока, ее изображение не будет содержать структуру TLS.  В разделе [поток](../../cpp/thread.md) для получения дополнительной информации.  
  
 IMAGE_TLS_DIRECTORY, определенный в заголовке winnt.h.  
  
## <a name="see-also"></a>См. также  
 [Параметры DUMPBIN](../../build/reference/dumpbin-options.md)