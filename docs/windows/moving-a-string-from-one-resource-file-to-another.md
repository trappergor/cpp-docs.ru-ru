---
title: Перемещение строки из одного файла ресурсов в другой | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], moving between files
- resource script files, moving strings
- string editing, moving strings between resources
- String editor, moving strings between files
ms.assetid: 94f8ee81-9b4c-4788-ba95-68c58db38029
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1481f04b88d6ab63486885d93b971c3023d3e0d2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879273"
---
# <a name="moving-a-string-from-one-resource-file-to-another"></a>Перемещение строки из одного файла ресурса в другой
### <a name="to-move-a-string-from-one-resource-script-file-to-another"></a>Перемещение строки из одного файла скрипта ресурсов в другой  
  
1.  Откройте таблицы строк в обоих RC-файлах. (Дополнительные сведения см. в разделе [Просмотр ресурсов в файле скрипта ресурсов за пределами проекта](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).)  
  
    > [!NOTE]
    >  Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Щелкните правой кнопкой мыши строку, необходимо переместить и выберите **Вырезать** в контекстном меню.  
  
3.  Поместите курсор в целевом **редактора строк** окна.  
  
4.  В RC-файле, к которому нужно вставить строку, щелкните правой кнопкой мыши и выберите **вставить** в контекстном меню.  
  
    > [!NOTE]
    >  Если **идентификатор** или **значение** перемещенной строки конфликтует с существующим **идентификатор** или **значение** в файле назначения, либо **Идентификатор** или **значение** перемещенной строки изменений. Если существует строка с тем же **идентификатор**, **идентификатор** перемещенной строки изменений. Если существует строка с тем же **значение**, **значение** перемещенной строки изменений.  
  
 Сведения о добавлении ресурсов в управляемые проекты (предназначенные общеязыковая среда выполнения), см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* . Сведения о том, как вручную добавлять файлы ресурсов в проекты управляемого кода, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделах [Пошаговое руководство. Локализация Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6);  
  
 **Требования**  
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Редактор строк](../windows/string-editor.md)   
 [Файлы ресурсов](../windows/resource-files-visual-studio.md)   
 [Настройка макетов окон](/visualstudio/ide/customizing-window-layouts-in-visual-studio)   

