---
title: "Создание элемента управления ActiveX MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.activex.project"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "элементы управления ActiveX [C++], создание"
  - "элементы управления MFC ActiveX [C++], создание"
ms.assetid: 8bd5a93c-d04d-414e-bb28-163fdc1c0dd5
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Создание элемента управления ActiveX MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Программы\-элементы управления ActiveX ― это модульные программы, разработанные для предоставления определенной функциональности родительскому приложению.  Например, можно создать элемент управления "кнопка" для использования в диалоговом окне, или элемент управления "панель инструментов" для использования на веб\-странице.  
  
 Самый простой способ создания элемента управления ActiveX MFC состоит в использовании [Мастера элементов управления ActiveX MFC](../../mfc/reference/mfc-activex-control-wizard.md).  
  
### Создание элемента управления ActiveX MFC при помощи мастера элементов управления ActiveX MFC  
  
1.  Следуйте инструкциям, приведенным в разделе справки [Создание проекта с использованием мастера приложений Visual C\+\+](../../ide/creating-desktop-projects-by-using-application-wizards.md).  
  
2.  В диалоговом окне **Новый проект** выберите значок **Элемент управления ActiveX библиотеки MFC** в области "Шаблоны", чтобы открыть мастер элементов ActiveX MFC.  
  
3.  Определите [параметры приложения](../../mfc/reference/application-settings-mfc-activex-control-wizard.md), [имена элементов управления](../../mfc/reference/control-names-mfc-activex-control-wizard.md) и [параметры элементов управления](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) с помощью мастера элементов управления ActiveX MFC.  
  
    > [!NOTE]
    >  Для сохранения параметров, заданных в мастере по умолчанию, пропустите этот шаг.  
  
4.  Нажмите кнопку **Готово** для завершения работы мастера и откройте новый проект в среде разработки.  
  
 После создания проекта можно просмотреть файлы, созданные в **обозревателе решений**.  Дополнительные сведения о файлах, создаваемых мастером для проекта, см. в созданном для проекта файле ReadMe.txt.  Дополнительные сведения о типах файлов см. в разделе [Типы файлов, создаваемых для проектов Visual C\+\+](../../ide/file-types-created-for-visual-cpp-projects.md).  
  
 После создания проекта можно с помощью мастеров кода добавить [функции](../../ide/add-member-function-wizard.md), [переменные](../../ide/add-member-variable-wizard.md), [события](../../ide/add-event-wizard.md), [свойства](../../ide/names-add-property-wizard.md) и [методы](../../ide/add-method-wizard.md).  Дополнительные сведения о настройке элементов управления ActiveX см. в разделе [Элементы управления ActiveX MFC](../../mfc/mfc-activex-controls.md).  
  
## См. также  
 [Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Страницы свойств](../../ide/property-pages-visual-cpp.md)   
 [Deploying Applications](http://msdn.microsoft.com/ru-ru/4ff8881d-0daf-47e7-bfe7-774c625031b4)