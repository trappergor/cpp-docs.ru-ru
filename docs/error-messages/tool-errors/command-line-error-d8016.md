---
title: Ошибка командной строки D8016 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D8016
dev_langs:
- C++
helpviewer_keywords:
- D8016
ms.assetid: eec51312-7471-4f92-94b2-d517cafc8ef5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d6f9709da189403f2594d76751430d30554bffe5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300622"
---
# <a name="command-line-error-d8016"></a>Ошибка командной строки D8016
несовместимые параметры командной строки 'параметр1' и 'параметр2'  
  
 Параметры командной строки нельзя указывать вместе.  
  
 Проверьте переменные среды, например CL, параметры.  
  
 **/ CLR** подразумевает **/EHa**, и нельзя использовать другие **/EH** параметр компилятора с **/CLR**. Дополнительные сведения см. в разделе [/clr (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 D8016 может возникнуть после обновления [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] 6.0 проекта: мастер обновления проекта может включить **/RTC** для каждого файла исходного кода в проекте, который переопределяет **/RTC** для проект.  Чтобы устранить, измените **/RTC** задания для каждого файла исходного кода в проекте по умолчанию, означающее параметров проекта для **/RTC** вступят в силу для каждого файла.  
  
 В разделе [/RTC (проверки ошибок во время выполнения)](../../build/reference/rtc-run-time-error-checks.md) сведения об изменении **/RTC** значение свойства.