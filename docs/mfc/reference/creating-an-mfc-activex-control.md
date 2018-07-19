---
title: Создание элемента управления ActiveX в MFC | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.activex.project
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], creating
- ActiveX controls [MFC], creating
ms.assetid: 8bd5a93c-d04d-414e-bb28-163fdc1c0dd5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c29aef2fcee829924021f9352145714a83698d38
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2018
ms.locfileid: "39026781"
---
# <a name="creating-an-mfc-activex-control"></a>Создание элемента управления ActiveX MFC
Программы управления ActiveX являются модульные программы, разработанные для предоставления определенной функциональности в родительское приложение. Например можно создать элемент управления, например кнопки для использования в диалоговом окне или панели инструментов для использования на веб-странице.  
  
 Самый простой способ создания элемента управления MFC ActiveX является использование [мастер элементов управления ActiveX MFC](../../mfc/reference/mfc-activex-control-wizard.md).  
  
### <a name="to-create-an-mfc-activex-control-using-the-mfc-activex-control-wizard"></a>Для создания элемента управления ActiveX MFC, с помощью мастера элементов управления ActiveX MFC  
  
1.  Следуйте инструкциям, приведенным в разделе справки [Создание проекта с использованием мастера приложений Visual C++](../../ide/creating-desktop-projects-by-using-application-wizards.md).  
  
2.  В **новый проект** выберите **элемента управления ActiveX MFC** значок в области «Шаблоны», чтобы открыть мастер элементов управления ActiveX MFC.  
  
3.  Определение вашего [параметры приложения](../../mfc/reference/application-settings-mfc-activex-control-wizard.md), [имена элементов управления](../../mfc/reference/control-names-mfc-activex-control-wizard.md), и [управлять параметрами](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) с помощью мастера элементов управления ActiveX MFC.  
  
    > [!NOTE]
    >  Для сохранения параметров, заданных в мастере по умолчанию, пропустите этот шаг.  
  
4.  Нажмите кнопку **Готово** закрыть мастер и открыть проект в среде разработки.  
  
 После создания проекта можно просмотреть файлы, созданные в **обозревателе решений**. Дополнительные сведения о файлах, создаваемых мастером для проекта, см. в созданном для проекта файле ReadMe.txt. Дополнительные сведения о типах файлов см. в разделе [типы файлов, создаваемых для проектов Visual C++](../../ide/file-types-created-for-visual-cpp-projects.md).  
  
 После создания проекта, можно использовать мастеры кода для добавления [функции](../../ide/add-member-function-wizard.md), [переменных](../../ide/add-member-variable-wizard.md), [события](../../ide/add-event-wizard.md), [свойства](../../ide/names-add-property-wizard.md), и [методы](../../ide/add-method-wizard.md). Дополнительные сведения о настройке элементов управления ActiveX, см. в разделе [элементы ActiveX в MFC](../../mfc/mfc-activex-controls.md).  
  
## <a name="see-also"></a>См. также  
 [Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Страницы свойств](../../ide/property-pages-visual-cpp.md)   
 [Развертывание приложений](http://msdn.microsoft.com/4ff8881d-0daf-47e7-bfe7-774c625031b4)

