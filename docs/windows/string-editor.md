---
title: "Редактор строк | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.string.F1
dev_langs: C++
helpviewer_keywords:
- String editor
- string tables
- string tables, String editor
- string editing
- string editing, string tables
- resource editors, String editor
- strings [C++], editing
ms.assetid: f71ab8de-3068-4e29-8e28-5a33d18dd416
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0a84ee72d44a7c7ba694df023ad50258513b40bf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="string-editor"></a>Редактор строк
Таблица строк — это ресурс Windows, содержащий список идентификаторов, значений и заголовков для всех строк в приложении. Например, в таблице строк могут содержаться подсказки, выводимые в строке состояния.  
  
 В процессе разработки приложения можно использовать несколько таблиц строк для разных языков и ситуаций. Однако исполняемый модуль имеет только одну таблицу строк. Работающее приложение может ссылаться на несколько таблиц строк, если они помещены в разные библиотеки DLL.  
  
 Таблицы строк упрощают локализацию приложения на разные языки. Если все строки находятся в таблице строк, вы можете локализовать приложение, переведя строки (и другие ресурсы) и не меняя исходный код. Обычно это удобнее, чем вручную искать и заменять различные строки в исходных файлах.  
  
 С помощью редактора можно выполнять следующие действия:  
  
-   [искать одну или несколько строк](../windows/finding-a-string.md);  
  
-   быстро [вставлять новые записи](../windows/adding-or-deleting-a-string.md) в таблицу строк;  
  
-   [перемещать строку из одного файла ресурсов в другой;](../windows/moving-a-string-from-one-resource-file-to-another.md)  
  
-   [редактировать свойства ID, Value и Caption на месте](../windows/changing-the-properties-of-a-string.md) и немедленно просматривать изменения;  
  
-   [изменять свойство заголовка для нескольких строк;](../windows/changing-the-caption-property-of-multiple-strings.md)  
  
-   [добавлять форматирование или специальные символы в строку.](../windows/adding-formatting-or-special-characters-to-a-string.md)  
  
    > [!NOTE]
    >  Windows не разрешает создавать пустые таблицы строк. Если вы создадите таблицу строк, не содержащую записей, она будет автоматически удалена при сохранении файла ресурсов.  
  
 Сведения о добавлении ресурсов в управляемые проекты (предназначенные общеязыковая среда выполнения), см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* . Сведения о том, как вручную добавлять файлы ресурсов в проекты управляемого кода, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделах [Пошаговое руководство. Локализация Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6);  
  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Редакторы ресурсов](../windows/resource-editors.md)   
 [Строки](http://msdn.microsoft.com/library/windows/desktop/ms646979.aspx)   
 [Сведения о строках](http://msdn.microsoft.com/library/windows/desktop/ms647465.aspx)

