---
title: "pgomgr | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- pgomgr program
- profile-guided optimizations, pgomgr
ms.assetid: 74589126-df18-42c9-8739-26d60e148d6a
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ab078acd8aaadef19659ad766233ea191b360e02
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="pgomgr"></a>pgomgr
Добавляет данные профиля из одного или нескольких файлов PGC в PGD-файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
pgomgr [options] pgcfiles pgdfile  
```  
  
#### <a name="parameters"></a>Параметры  
 `options`  
 Чтобы pgomgr можно указать следующие параметры:  
  
 **/ help —**отображаются параметры доступные pgomgr (сокращенно /?).  
  
 **/ clear —**вызывает PGD-файл очистить все данные профиля. Нельзя указать .pgc файл появляется, когда **/clear** указано.  
  
 **/ detail**— отображает подробную статистику, включая сведения о действии диаграмм потока.  
  
 **/ summary**— отображает по функциям статистики.  
  
 **/ unique**— при использовании с **/summary**, внутренних имен функций для отображения.  Значение по умолчанию, когда / unique не используется, предназначена для имен объявление функции для отображения.  
  
 **/ merge**[**:***n*]**—**в результате данные в PGC-файл или файлы для добавления в PGD-файл.  Необязательный параметр  *n* , позволяет указать, должны быть добавлены данные hat  *n*  раз.  Например, если сценарий будет выполняться часто 6 раз, можно один раз выполнить тестовый запуск и добавьте его в PGD-файл в шесть раз с **pgomgr /merge:6**.  
  
 `pgcfiles`  
 Один или несколько PGC-файлов, данные профиля, которые необходимо объединить в PGD-файл. Можно указать один или несколько PGC-файлов. Если все PGC-файлы не указан, программа pgomgr всех файлов, имена которых совпадают с PGD-файла.  
  
 `pgdfile`  
 PGD-файл, в который слияние данных из PGC-файл или файлы.  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Это средство можно запустить только из командной строки [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]. В системной командной строке или проводнике это невозможно.  
  
## <a name="example"></a>Пример  
 В следующем примере в PGD-файл был очищен данных профиля.  
  
```  
pgomgr /clear myapp.pgd  
```  
  
 В следующем примере данные профиля в файле myapp1.pgc в PGD-файл был добавлен в 3 раза.  
  
```  
pgomgr /merge:3 myapp1.pgc myapp.pgd  
```  
  
 В следующем примере добавляется файл myapp.pgd данных профиля из всех файлов myapp # .pgc.  
  
```  
pgomgr -merge myapp1.pgd  
```  
  
## <a name="see-also"></a>См. также  
 [Средства для профильной оптимизации вручную](../../build/reference/tools-for-manual-profile-guided-optimization.md)