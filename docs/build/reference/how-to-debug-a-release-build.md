---
title: 'Как: отладка построения выпуска | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- debugging [C++], release builds
- release builds, debugging
ms.assetid: d333e4d1-4e6c-4384-84a9-cb549702da25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e733375f01d4b2b8ec7090f7f70ad1ec5280cd9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-debug-a-release-build"></a>Практическое руководство. Отладка построения выпуска
Можно отлаживать сборки выпуска приложения.  
  
### <a name="to-debug-a-release-build"></a>Отладка построения выпуска  
  
1.  Откройте **страницы свойств** диалоговое окно для проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **C/C++** узла. Задать **формат отладочной информации** для [C7 совместимо (/ Z7)](../../build/reference/z7-zi-zi-debug-information-format.md) или **базы данных программы (/Zi)**.  
  
3.  Разверните **компоновщика** и нажмите кнопку **Общие** узла. Задать **Включить инкрементную компоновку** для [нет (/ INCREMENTAL: NO)](../../build/reference/incremental-link-incrementally.md).  
  
4.  Выберите **Отладка** узла. Задать **создать отладочную информацию** для [Да (/ DEBUG)](../../build/reference/debug-generate-debug-info.md).  
  
5.  Выберите **оптимизации** узла. Задать **ссылки** для [/OPT: ref](../../build/reference/opt-optimizations.md) и **включить свертывание записей COMDAT** для [/OPT: ICF](../../build/reference/opt-optimizations.md).  
  
6.  Теперь можно отлаживать приложения построения выпуска. Для обнаружения проблемы, пошаговое выполнение кода (или используйте только по требованию отладку), пока не найдете место возникновения сбоя и затем определите неверные параметры кода.  
  
     Если приложение работает в отладочной сборке, но завершается сбоем в сборке выпуска, один из оптимизации компилятора может точкой дефектах в исходном коде. Чтобы локализовать проблему, отключите выбранные оптимизации для каждого файла исходного кода до нужного файла и оптимизации, которая причиной проблемы. (Чтобы ускорить процесс, вы можно разделить файлы на две группы, отключить оптимизацию для одной из групп и после обнаружения проблемы в группе продолжать такое разделение, пока не изолируете проблему файл.)  
  
     Можно использовать [/RTC](../../build/reference/rtc-run-time-error-checks.md) с целью предоставить такие ошибки в отладочных построениях.  
  
     Дополнительные сведения см. в разделе [оптимизация кода](../../build/reference/optimizing-your-code.md).  
  
## <a name="see-also"></a>См. также  
 [Устранение проблем сборки выпуска](../../build/reference/fixing-release-build-problems.md)