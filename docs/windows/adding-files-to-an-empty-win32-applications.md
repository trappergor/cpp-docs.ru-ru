---
title: Добавление файлов в пустые приложения Win32 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- empty projects, adding files
- projects [C++], adding items
- blank projects
- files [C++], adding to projects
ms.assetid: 070098e8-0396-49fe-a697-3daa2f1be6de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 625b75a81773b45483c8b70c12530acfc9f75994
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="adding-files-to-an-empty-win32-applications"></a>Добавление файлов в пустые приложения Win32
### <a name="to-add-your-files-to-an-empty-windows-desktop-application"></a>Добавление файлов в пустое классическое приложение Windows  
  
1.  Выберите каталог в **обозревателе решений**.  
  
2.  Щелкните правой кнопкой мыши имя каталога, выберите в контекстном меню команду **Добавить** , а затем выберите пункт **Существующий элемент**.  
  
3.  В диалоговом окне **Добавление существующего элемента**перейдите к файлам, которые нужно добавить в проект.  
  
4.  Нажмите кнопку **ОК**.  
  
 Для добавления в проект файлов, не являющихся исходными файлами, файлами заголовков или файлами ресурсов, щелкните правой кнопкой мыши узел "Решение" в обозревателе решений и добавьте файлы в проект аналогичным образом. Для хранения прочих файлов проекта будет создана папка Miscellaneous.  
  
> [!NOTE]
>  Прежде чем приступать к сборке проекта, необходимо будет указать параметры сборки этих файлов, чтобы они были корректным образом включены в готовое приложение. Дополнительные сведения см. в разделах [Задание параметров проекта при помощи страниц свойств](../ide/property-pages-visual-cpp.md) и [Сборка программы C/C++](../build/building-c-cpp-programs.md).  
  
## <a name="see-also"></a>См. также  
 [Создание пустого классического приложения Windows](../windows/creating-an-empty-windows-desktop-application.md)   
 [Развертывание приложений](http://msdn.microsoft.com/en-us/4ff8881d-0daf-47e7-bfe7-774c625031b4)