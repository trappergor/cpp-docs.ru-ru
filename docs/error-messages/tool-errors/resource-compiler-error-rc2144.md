---
title: "Ошибка компилятора ресурсов RC2144 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RC2144
dev_langs: C++
helpviewer_keywords: RC2144
ms.assetid: 1b3ff39a-92cd-4a04-b1a3-b1fa6a805813
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c29a1c1f392372b8dfddd84fa9693010e6a52bfa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-error-rc2144"></a>Ошибка компилятора ресурсов RC2144
PRIMARY LANGUAGE ID не является числом  
  
 PRIMARY LANGUAGE ID должен быть шестнадцатеричным идентификатором языка. В разделе [языка и страны или региона строки](../../c-runtime-library/locale-names-languages-and-country-region-strings.md) в *Справочник по библиотеке времени выполнения* список допустимых идентификаторов языка.  
  
 Эта ошибка также может возникнуть, если с помощью какого-либо средства ресурсы были добавлены в RC-файл или удалены из RC-файла. Чтобы устранить эту проблему, откройте RC-файл в текстовом редакторе и вручную удалите все неиспользуемые ресурсы.