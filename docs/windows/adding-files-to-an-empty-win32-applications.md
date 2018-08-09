---
title: Добавление файлов в пустые приложения Win32 | Документация Майкрософт
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
ms.openlocfilehash: 1efde876cadd5a8620bef83c37a61b8b471dba8b
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40019242"
---
# <a name="adding-files-to-an-empty-win32-applications"></a>Добавление файлов в пустые приложения Win32
### <a name="to-add-your-files-to-an-empty-windows-desktop-application"></a>Добавление файлов в пустое классическое приложение Windows  
  
1.  Выберите каталог в **обозревателе решений**.  
  
2.  Щелкните правой кнопкой мыши имя каталога, выберите в контекстном меню команду **Добавить** , а затем выберите пункт **Существующий элемент**.  
  
3.  В диалоговом окне **Добавление существующего элемента**перейдите к файлам, которые нужно добавить в проект.  
  
4.  Нажмите кнопку **ОК**.  
  
 Чтобы добавить файлы, ни источник, заголовок или файлы ресурсов в проект, щелкните правой кнопкой мыши **решение** узел в **обозревателе решений** и добавьте файлы в проект таким же образом. Объект **Разное** будет создана папка для хранения других файлов в проекте.  
  
> [!NOTE]
>  Прежде чем приступать к сборке проекта, необходимо будет указать параметры сборки этих файлов, чтобы они были корректным образом включены в готовое приложение. Дополнительные сведения см. в разделах [Задание параметров проекта при помощи страниц свойств](../ide/property-pages-visual-cpp.md) и [Сборка программы C/C++](../build/building-c-cpp-programs.md).  
  
## <a name="see-also"></a>См. также  
 [Создание классического приложения Windows пустой](../windows/creating-an-empty-windows-desktop-application.md)   
 [Развертывание приложений](http://msdn.microsoft.com/4ff8881d-0daf-47e7-bfe7-774c625031b4)