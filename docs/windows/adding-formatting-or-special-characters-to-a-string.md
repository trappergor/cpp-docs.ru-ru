---
title: "Добавление форматирования или специальных символов в строку | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- special characters, adding to strings
- ASCII characters, adding to strings
- strings [C++], formatting
- strings [C++], special characters
ms.assetid: c40f394a-8b2c-4896-ab30-6922863ddbb5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ca91ef9742f2dfb10a0af12c74ca58f80035d131
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="adding-formatting-or-special-characters-to-a-string"></a>Добавление форматирования или специальных символов в строки
### <a name="to-add-formatting-or-special-characters-to-a-string"></a>Добавление форматирования или специальных символов в строку  
  
1.  Откройте таблицу строк, дважды щелкнув его значок в [представление ресурсов](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Выберите строку, которую требуется изменить.  
  
3.  В [окно свойств](/visualstudio/ide/reference/properties-window), добавьте любой из стандартных escape-последовательностей перечисленные ниже текст в **заголовок** поле и нажмите клавишу **ввод**.  
  
    |Чтобы получить это|Тип значения|  
    |-----------------|---------------|  
    |Новая строка|\n|  
    |Возврат каретки|\r|  
    |Вкладка|\t|  
    |Обратная косая черта (\\)|\\\|  
    |Символ ASCII|\ddd (восьмеричная)|  
    |Оповещение (колокольчик)|\a|  
  
> [!NOTE]
>  Редактор строк не поддерживает полный набор символов ASCI ЦЕЛИКОМ. Можно использовать только перечисленных выше.  
  
 Сведения о добавлении ресурсов в управляемые проекты (предназначенные общеязыковая среда выполнения), см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* . Сведения о том, как вручную добавлять файлы ресурсов в проекты управляемого кода, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделах [Пошаговое руководство. Локализация Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6);  
  
 **Требования**  
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Редактор строк](../windows/string-editor.md)   

