---
title: "Ошибка командной строки D8016 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- D8016
dev_langs:
- C++
helpviewer_keywords:
- D8016
ms.assetid: eec51312-7471-4f92-94b2-d517cafc8ef5
caps.latest.revision: 11
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 79dad5a5134e91b67a395870e4ff7fa8e14066fb
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="command-line-error-d8016"></a>Ошибка командной строки D8016
несовместимые параметры командной строки 'параметр1' и 'параметр2'  
  
 Параметры командной строки нельзя указывать вместе.  
  
 Проверьте переменные среды, например CL, параметры.  
  
 **/ CLR** подразумевает **/EHa**, и нельзя использовать другие **дополнительных** параметр компилятора с **/CLR**. Дополнительные сведения см. в разделе [/clr (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 D8016 может возникнуть после обновления [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] проекта 6.0: мастер обновления проекта может включить **/RTC** для каждого файла исходного кода в проекте, который переопределяет **/RTC** для проекта.  Чтобы устранить, измените **/RTC** задания для каждого файла исходного кода в проекте по умолчанию, означающее параметров проекта для **/RTC** вступят в силу для каждого файла.  
  
 В разделе [/RTC (проверки ошибок во время выполнения)](../../build/reference/rtc-run-time-error-checks.md) сведения об изменении **/RTC** значение свойства.
