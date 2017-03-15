---
title: "Ошибка построения проекта PRJ0003 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- PRJ0003
dev_langs:
- C++
helpviewer_keywords:
- PRJ0003
ms.assetid: fc5a84bb-c6d3-41d6-8dd6-475455820778
caps.latest.revision: 7
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: aac7a37a94013a1acad8ee866d9ac7ce28fda94c
ms.lasthandoff: 02/24/2017

---
# <a name="project-build-error-prj0003"></a>Ошибка построения проекта PRJ0003
Ошибка при создании «Командная строка».  
  
 В команду ***командной строки***, которая была создана из входных данных в **страницы свойств** диалогового окна, возвращается код ошибки, но не сведения будут отображаться в окне вывода.  
  
 Возможные причины этой ошибки:  
  
-   Проект зависит от сервера ATL. Начиная с версии [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)], ATL Server больше не включены в Visual Studio, но была выпущена в виде исходного проекта на сайте CodePlex. Чтобы загрузить исходный код ATL Server и средств, перейдите к [http://go.microsoft.com/fwlink/?LinkID=81979](http://go.microsoft.com/fwlink/?LinkID=81979).  
  
-   Нехватка системных ресурсов. Закройте некоторые приложения, чтобы решить эту проблему.  
  
-   Недостаточный уровень привилегий безопасности. Проверьте наличие достаточных прав доступа.  
  
-   Пути к исполняемым файлам, указанного в [каталоги VC ++](http://msdn.microsoft.com/en-us/e027448b-c811-4c3d-8531-4325ad3f6e02) не включают путь средство, которое вы пытаетесь запустить.  
  
-   В проектах makefile отсутствует команда для запуска на любой **построения командной строки** или **командной строке перестроения**.  
  
## <a name="see-also"></a>См. также  
 [Ошибки построения и предупреждения проекта (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)
