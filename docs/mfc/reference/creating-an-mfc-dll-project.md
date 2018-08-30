---
title: Создание проекта библиотеки DLL MFC | Документация Майкрософт
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
ms.openlocfilehash: 5fa06417b93012c7d564a45c4e58f03edf1e2a39
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215682"
---
# <a name="creating-an-mfc-dll-project"></a>Создание проекта библиотеки DLL MFC
Библиотека DLL MFC — это двоичный файл, который выступает в качестве общей библиотеки функций, которые могут использоваться одновременно несколькими приложениями. Самый простой способ создания проекта MFC DLL является использование мастера MFC DLL.  
  
> [!NOTE]
>  Вид функций в интегрированной среде разработки может зависеть от текущих параметров или выпуска и могут отличаться от описанных в справке. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](https://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-an-mfc-dll-project-using-the-mfc-dll-wizard"></a>Чтобы создать проект библиотеки DLL MFC, с помощью мастера MFC DLL  
  
1.  Следуйте инструкциям, приведенным в разделе справки [Создание проекта с использованием мастера приложений Visual C++](../../ide/creating-desktop-projects-by-using-application-wizards.md).  
  
 **Примечание** в **новый проект** выберите `MFC DLL` значок в области «Шаблоны», чтобы открыть мастер библиотек DLL MFC.  
  
1.  Задайте параметры приложения с помощью [параметры приложения](../../mfc/reference/application-settings-mfc-dll-wizard.md) странице [мастера MFC DLL](../../mfc/reference/mfc-dll-wizard.md).  
  
    > [!NOTE]
    >  Для сохранения параметров, заданных в мастере по умолчанию, пропустите этот шаг.  
  
2.  Нажмите кнопку **Готово** закрыть мастер и откройте новый проект в **обозревателе решений**.  
  
 После создания проекта можно просмотреть файлы, созданные в обозревателе решений. Дополнительные сведения о файлах, создаваемых мастером для проекта, см. в созданном для проекта файле ReadMe.txt. Дополнительные сведения о типах файлов см. в разделе [типы файлов, создаваемых для проектов Visual C++](../../ide/file-types-created-for-visual-cpp-projects.md).  
  
## <a name="see-also"></a>См. также  
 [Типы проектов Visual C++](/visualstudio/debugger/debugging-preparation-visual-cpp-project-types)   
 [Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Страницы свойств](../../ide/property-pages-visual-cpp.md)   
 [Развертывание приложений](https://msdn.microsoft.com/4ff8881d-0daf-47e7-bfe7-774c625031b4)

