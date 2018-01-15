---
title: "Изменение свойств для нескольких сочетаний клавиш | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- keyboard shortcuts [C++], property changing
- accelerator tables [C++], changing properties
ms.assetid: b55c9bd6-b430-48bb-b942-0e6f21d7abf9
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8fbe5ab2202da457c8970d84d304ec97fdedd4a1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="changing-the-properties-of-multiple-accelerator-keys"></a>Изменение свойств для нескольких сочетаний клавиш
### <a name="to-change-the-properties-of-multiple-accelerator-keys"></a>Изменение свойств для нескольких сочетаний клавиш  
  
1.  Откройте таблицу сочетаний клавиш, дважды щелкнув его значок в [представление ресурсов](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Выберите сочетания клавиш, которые вы хотите изменить, удерживая нажатой **CTRL** ключа, щелкните каждый из них.  
  
3.  Последовательно выберите пункты [окно свойств](/visualstudio/ide/reference/properties-window) и введите нужные значения всех сочетаний для совместного использования.  
  
    > [!NOTE]
    >  Каждое значение модификатора отображается как логическое свойство в окне «Свойства». При изменении [модификатор](../windows/accelerator-modifier-property.md) значение в окне «Свойства» в таблице сочетаний клавиш новый модификатор рассматривает как дополнение к ранее использовавшимся модификаторам. По этой причине при установке любого значения модификатора необходимо будет задать все их, чтобы убедиться, что для всех сочетаний клавиш заданы те же параметры модификатор.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
 **Требования**  
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Редактирование таблиц сочетаний клавиш](../windows/editing-accelerator-tables.md)   
 [Редактор сочетаний клавиш](../windows/accelerator-editor.md)