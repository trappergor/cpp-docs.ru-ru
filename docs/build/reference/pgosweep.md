---
title: "pgosweep | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- pgosweep program
- profile-guided optimizations, pgosweep
ms.assetid: f39dd3b7-1cd9-4c3b-8e8b-fb794744b757
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 78ae6c36011e3c10359988cf2c501514d1bcf70a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="pgosweep"></a>pgosweep
Используется в профильной оптимизации для записи всех данных профиля из выполняющейся программы в файл PGC.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
pgosweep [options] image pgcfile  
```  
  
#### <a name="parameters"></a>Параметры  
 `options`  
 Необязательный параметр, который может быть пустым. Допустимые значения для `options` , как показано ниже:  
  
-   **/?** или **/Help,** отображает сообщение справки.  
  
-   **/NORESET,** сохраняет значение счетчика в структурах данных времени выполнения.  
  
 `image`  
 Полный путь файла .exe или .dll, который был создан с помощью параметра компилятора/LTCG: PGINSTRUMENT.  
  
 `pgcfile`  
 PGC-файл, где эта команда записывает данные счетчиков.  
  
## <a name="remarks"></a>Примечания  
 Эта команда работает с программами, которые были созданы с помощью параметра компилятора/LTCG: PGINSTRUMENT. Он прерывает выполняющуюся программу и записывает данные профиля в новый PGC-файл. По умолчанию команда обнуляет счетчики после каждой операции записи. При указании **/noreset** параметр, команда будет записывать значения, но не переустановит их в выполняющейся программе. Этот параметр позволит вам повторяющихся данных при извлечении данных профиля в более поздней версии.  
  
 Вариантом использования `pgosweep` — для получения сведений о профиле только для среды выполнения приложения. Например, можно выполнить `pgosweep` вскоре после запуска приложения и удалить этот файл. Это приведет к удалению данных профиля, связанных с издержками при запуске. Затем можно выполнить `pgosweep` до завершения работы приложения. Теперь собранные данные включают сведения о профиле только во время выполнения.  
  
 Если имя PGC-файл (`pgcfile`) можно использовать стандартный формат *appname! n*.pgc. Если вы используете этот формат, компилятор будет искать эти данные на этапе LTCG: PGO. Если вы не используете стандартного формата, необходимо использовать [pgomgr](../../build/reference/pgomgr.md) для слияния PGC-файлы.  
  
## <a name="example"></a>Пример  
  
```  
pgosweep myapp.exe myapp!1.pgc  
```  
  
 В этом примере `pgosweep` myapp!1.pgc записывает текущие данные профиля для myapp.exe.  
  
## <a name="see-also"></a>См. также  
 [Средства для профильной оптимизации вручную](../../build/reference/tools-for-manual-profile-guided-optimization.md)