---
title: "Ошибка компилятора ресурсов RC2144 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC2144"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC2144"
ms.assetid: 1b3ff39a-92cd-4a04-b1a3-b1fa6a805813
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора ресурсов RC2144
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

PRIMARY LANGUAGE ID не является числом  
  
 PRIMARY LANGUAGE ID должен быть шестнадцатеричным идентификатором языка.  Допустимые идентификаторы языков см. в разделе [Языки и настройки для стран и регионов](../../c-runtime-library/locale-names-languages-and-country-region-strings.md) в *справочнике по библиотеке среды выполнения*.  
  
 Эта ошибка также может возникнуть, если с помощью какого\-либо средства ресурсы были добавлены в RC\-файл или удалены из RC\-файла.  Чтобы устранить эту проблему, откройте RC\-файл в текстовом редакторе и вручную удалите все неиспользуемые ресурсы.