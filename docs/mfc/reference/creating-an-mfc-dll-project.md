---
title: Создание проекта библиотеки DLL MFC | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfcdll.project
dev_langs:
- C++
helpviewer_keywords:
- MFC DLLs [MFC], creating projects
- DLLs [MFC], MFC
- projects [MFC], creating
- DLLs [MFC], creating
ms.assetid: 05540b93-4781-4a90-aadf-55158313f5b2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c5c560fecdaed6ea74442596aab685a08300b3fb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="creating-an-mfc-dll-project"></a>Создание проекта библиотеки DLL MFC
MFC-библиотеки DLL является двоичным файлом, который выступает в качестве общей библиотеки функций, которые могут использоваться одновременно несколькими приложениями. Самый простой способ создать проект библиотеки DLL MFC является использование мастера DLL MFC.  
  
> [!NOTE]
>  Вид функций в Интегрированной среде разработки может зависеть от текущих параметров или выпуска и могут отличаться от описанных в справке. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-an-mfc-dll-project-using-the-mfc-dll-wizard"></a>Создание проекта библиотеки DLL MFC с помощью мастера DLL MFC  
  
1.  Следуйте инструкциям в разделе справки [Создание проекта с использованием мастера приложений Visual C++](../../ide/creating-desktop-projects-by-using-application-wizards.md).  
  
 **Примечание** в **новый проект** выберите `MFC DLL` значок в области шаблонов, чтобы открыть мастер библиотек DLL MFC.  
  
1.  Задайте параметры приложения с помощью [параметры приложения](../../mfc/reference/application-settings-mfc-dll-wizard.md) страница [мастера библиотек DLL MFC](../../mfc/reference/mfc-dll-wizard.md).  
  
    > [!NOTE]
    >  Для сохранения параметров, заданных в мастере по умолчанию, пропустите этот шаг.  
  
2.  Нажмите кнопку **Готово** завершить работу мастера и откройте новый проект в **обозревателе решений**.  
  
 После создания проекта можно просмотреть файлы, созданные в обозревателе решений. Дополнительные сведения о файлах, создаваемых мастером для проекта, см. в созданном для проекта файле ReadMe.txt. Дополнительные сведения о типах файлов см. в разделе [типы файлов, создаваемых для проектов Visual C++](../../ide/file-types-created-for-visual-cpp-projects.md).  
  
## <a name="see-also"></a>См. также  
 [Типы проектов Visual C++](/visualstudio/debugger/debugging-preparation-visual-cpp-project-types)   
 [Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Страницы свойств](../../ide/property-pages-visual-cpp.md)   
 [Развертывание приложений](http://msdn.microsoft.com/en-us/4ff8881d-0daf-47e7-bfe7-774c625031b4)

