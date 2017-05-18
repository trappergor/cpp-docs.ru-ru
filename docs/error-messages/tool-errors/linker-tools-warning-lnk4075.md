---
title: "Предупреждение средств компоновщика LNK4075 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4075
dev_langs:
- C++
helpviewer_keywords:
- LNK4075
ms.assetid: f39ad3f9-c263-4cf0-9d70-259fc56ac96d
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9dee257bec0f09bd729bf10c4a1468ecb20dfa61
ms.openlocfilehash: 84dea754a1d2268c92e703dd04b0169ccc258ab3
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-warning-lnk4075"></a>Предупреждение средств компоновщика LNK4075
Пропуск вариант «1» из-за спецификации вариант «2»  
  
 Второй параметр переопределяет первый параметр.  
  
 Указаны взаимоисключающие параметры компоновщика.  Проверьте параметры компоновщика.  Когда указаны параметры компоновщика зависит от способа построения проекта.  
  
-   При создании в среде разработки, просмотрите страницы свойств компоновщика для проекта и увидеть, где были указаны оба параметра компоновщика.  В разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md) подробнее.  
  
-   При построении из командной строки, просмотрите параметры компоновщика, указанные в ней.  
  
-   При построении с помощью скриптов построения, рассмотрим сценарий так, чтобы увидеть, где указаны параметры компоновщика.  
  
 Если вы обнаружите, где указаны взаимоисключающие параметры компоновщика, удалите один из параметров компоновщика.  
  
 Некоторые конкретные примеры:  
  
-   При связывании модуля, скомпилированного с **/ZI**, что подразумевает использование внутреннего параметра/EDITANDCONTINUE, и модуля, скомпилированного с/OPT: REF, / OPT: ICF или/INCREMENTAL: No, что подразумевает не/EDITANDCONTINUE, вы получите LNK4075.  В разделе [/Z7, / Zi, /ZI (формат отладочной информации)](../../build/reference/z7-zi-zi-debug-information-format.md) для получения дополнительной информации.
