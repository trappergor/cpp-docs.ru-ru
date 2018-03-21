---
title: "VCPROFILE_PATH | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VCPROFILE_PATH
dev_langs:
- C++
helpviewer_keywords:
- VCPROFILE_PATH environment variable
ms.assetid: 25217aa4-7e86-4eba-854d-10b3c457e4df
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ea682b70f4417ef49bfca530af5f12f21699a389
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="vcprofilepath"></a>VCPROFILE_PATH
Укажите каталог, чтобы создать PGC-файлы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
VCPROFILE_PATH=path  
```  
  
#### <a name="parameters"></a>Параметры  
 `path`  
 Путь к каталогу, в который .pgc файлы будут добавлены.  
  
## <a name="remarks"></a>Примечания  
 По умолчанию PGC-файлы создаются в каталоге, где профилируемый двоичный файл.  Однако, если абсолютный путь двоичный файл не существует, как может иметь место при запуске сценариев профиля на другом компьютере, из которой был создан двоичный файл, можно назначить `VCPROFILE_PATH` путь, который существует.  
  
## <a name="example"></a>Пример  
  
```  
set VCPROFILE_PATH=c:\  
```  
  
## <a name="see-also"></a>См. также  
 [Переменные среды для профильной оптимизации](../../build/reference/environment-variables-for-profile-guided-optimizations.md)