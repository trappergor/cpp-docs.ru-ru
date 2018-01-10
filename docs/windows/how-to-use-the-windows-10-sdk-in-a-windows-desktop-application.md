---
title: "Как: использование Windows 10 SDK в настольном приложении Windows | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
ms.assetid: eed6421e-9355-44a6-9582-3f1d453a6d44
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1f5e6f09b371c4d295b4bcdff469396a2671d22a
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2018
---
# <a name="how-to-use-the-windows-10-sdk-in-a-windows-desktop-application"></a>Практическое руководство. Использование пакета SDK для Windows 10 в классическом приложении Windows
При создании классического проекта Windows в Visual Studio 2017 г. он настроен по умолчанию для сборки с версией пакета SDK Windows 10, установленного при рабочей нагрузке C++ Desktop установки или последнего обновления. Эта версия пакета SDK Windows совместима со всеми последними выпусками Windows. Если требуется более раннюю версию пакета SDK, можно открыть проект | Свойства и выберите из версии пакета SDK, доступные в раскрывающемся списке версию пакета SDK Windows.  
  
 Начиная с Visual Studio 2015 и пакета SDK Windows 10, библиотека CRT была разделена на две части одного (ucrtbase), содержащая функции, допустимые для использования в универсальных приложениях Windows и которая содержит все остальное (vcruntime140). Поскольку пакет SDK для Windows 10 содержит новые функции, например многие функции C99, для их использования необходимо выполнить следующие действия. См. статью [CRT Library Features](../c-runtime-library/crt-library-features.md) (Функции библиотеки CRT).  
  
### <a name="to-target-the-windows-10-sdk"></a>Изменение целевой платформы для пакета SDK для Windows 10  
  
1.  Убедитесь, что установлен пакет SDK для Windows 10. Пакет SDK для Windows 10 устанавливается как часть [инструменты для Windows 10](http://go.microsoft.com/fwlink/p/?linkid=617631).  
  
2.  Откройте контекстное меню узла проекта и выберите пункт **Изменить целевую платформу для версии пакета SDK**.  
  
     ![Изменить целевую версию пакета SDK](../windows/media/retargetingwindowssdk1.PNG "RetargetingWindowsSDK1")  
  
     Откроется диалоговое окно **Просмотр действий решения** .  
  
     ![Просмотр действий решения](../windows/media/retargetingwindowssdk2.PNG "RetargetingWindowsSDK2")  
  
3.  В **версия целевой платформы** раскрывающемся списке выберите версию пакета SDK Windows 10, вы будете работать. Нажмите кнопку «ОК» для применения изменений.  
  
     Обратите внимание, что 8.1 в данном контексте относится к версии пакета SDK Windows, которая также обратно совместима с Windows 8, Windows Server 2012, Windows 7, Windows Server 2008 и Windows Vista.  
  
     Если этот шаг выполнен успешно, в окне вывода появится следующее сообщение.  
  
     `Retargeting End: 1 completed, 0 failed, 0 skipped`  
  
4.  Откройте свойства проекта и в разделе **Свойства конфигурации, Общие** обратите внимание на значения из параметра **Версия целевой платформы Windows**. Изменение значения на данном этапе действует аналогично данной процедуре. См. раздел [General Property Page (Project)](../ide/general-property-page-project.md).  
  
     ![Целевая версия платформы](../windows/media/retargetingwindowssdk3.PNG "RetargetingWindowsSDK3")  
  
     Это действие приводит к изменению значений макросов проекта, содержащих пути к файлам заголовка и файлам библиотеки. Чтобы увидеть измененные компоненты, в разделе каталогов Visual C++ диалогового окна «Свойства проекта» выберите одно из свойств, таких как каталоги включения, откройте раскрывающийся список и выберите \<изменить >. Откроется диалоговое окно **Каталоги включения** .  
  
     ![Включить диалоговое окно каталогов](../windows/media/retargetingwindowssdk4.PNG "RetargetingWindowsSDK4")  
  
     Выберите **макросы >>** кнопки и прокрутите вниз список макросов макросы пакета SDK для Windows, чтобы просмотреть все новые значения.  
  
     ![Макросы пакета SDK Windows](../windows/media/retargetingwindowssdk5.PNG "RetargetingWindowsSDK5")  
  
5.  При необходимости повторите для других проектов и перестройте решение.  
  
### <a name="to-target-the-windows-81-sdk"></a>Изменение целевой платформы для пакета SDK для Windows 8.1  
  
1.  Откройте контекстное меню узла проекта и выберите пункт **Изменить целевую платформу для версии пакета SDK**.  
  
2.  В раскрывающемся списке «Версия целевой платформы» выберите 8.1.  
  
## <a name="see-also"></a>См. также  
 [Классические приложения Windows (Visual C++)](../windows/how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)
