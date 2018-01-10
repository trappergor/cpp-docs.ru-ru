---
title: "Создание Библиотеку ресурсов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- resource-only DLLs [C++], creating
- DLLs [C++], creating
ms.assetid: e6b1d4da-7275-467f-a58c-a0a8a5835199
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dd65085c9a0ecc0479c7d22feb5587d1e94447de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-resource-only-dll"></a>Создание библиотек DLL, содержащих только ресурсы  
  
Библиотеку ресурсов является библиотекой DLL, содержащую только ресурсы, такие как значки, растровые изображения, строки и диалоговые окна. Используя Библиотеку ресурсов является хорошим способом совместно использовать один и тот же набор ресурсов несколькими программами. Также рекомендуется использовать приложение с ресурсы, локализованные для нескольких языков (см. [локализованные ресурсы в приложениях MFC: вспомогательные библиотеки DLL](../build/localized-resources-in-mfc-applications-satellite-dlls.md)).  
  
Чтобы создать Библиотеку ресурсов, создайте новый проект библиотеки DLL Win32 (не MFC) и добавьте ресурсы в проект.  
  
-   Выберите проект Win32 в **новый проект** диалоговое окно и укажите тип проекта библиотеки DLL в мастере проекта Win32.  
  
-   Создайте новый скрипт ресурсов, содержащий ресурсы (например, строка или меню) для библиотеки DLL и сохраните RC-файл.  
  
-   На **проекта** меню, нажмите кнопку **Добавление существующего элемента**, затем вставьте новый RC-файл в проект.  
  
-   Укажите [/NOENTRY](../build/reference/noentry-no-entry-point.md) компоновщика. / NOENTRY запрещает компоновщику добавлял ссылку на `_main` в библиотеку DLL; этот параметр необходим, чтобы создать Библиотеку ресурсов.  
  
-   Построение библиотеки DLL.  
  
Приложение, которое использует Библиотеку ресурсов, следует вызывать [LoadLibrary](../build/loadlibrary-and-afxloadlibrary.md) явной ссылкой на библиотеку DLL. Доступ к ресурсам, вызовите универсальные функции `FindResource` и `LoadResource`, которого работают для любых ресурсов, или вызовите один из следующих функций конкретного ресурса:  
  
-   `FormatMessage`  
  
-   `LoadAccelerators`  
  
-   `LoadBitmap`  
  
-   `LoadCursor`  
  
-   `LoadIcon`  
  
-   `LoadMenu`  
  
-   `LoadString`  
  
Приложение должно вызывать `FreeLibrary` после завершения использования ресурсов.  
  
## <a name="see-also"></a>См. также  
  
[Работа с файлами ресурсов](../windows/working-with-resource-files.md)  
[DLL в Visual C++](../build/dlls-in-visual-cpp.md)