---
title: Поддержка MFC в проекты ATL | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.atl.addmfc
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, MFC support
ms.assetid: f90b4276-cb98-4c11-902c-9ebcfe6f954b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d42afec863695b1cab05c2d3cf2f65f3d64a1507
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360645"
---
# <a name="mfc-support-in-atl-projects"></a>Поддержка MFC в проекты ATL
При выборе **поддержку MFC** в мастер проектов ATL, проект объявляет приложение как объект приложения MFC (класс). Проект инициализирует библиотеку MFC и создает класс (класс *ProjName*), производный от [CWinApp](../../mfc/reference/cwinapp-class.md).  
  
 Этот параметр доступен без атрибутов ATL только для проектов DLL.  
  
```  
class CProjNameApp : public CWinApp  
{  
public:  
 
// Overrides  
    virtual BOOL InitInstance();
virtual int ExitInstance();
DECLARE_MESSAGE_MAP() 
};  
 
BEGIN_MESSAGE_MAP(CProjNameApp, CWinApp)  
END_MESSAGE_MAP()  
 
CProjNameApp theApp;  
 
BOOL CProjNameApp::InitInstance()  
{  
    return CWinApp::InitInstance();

}  
 
int CProjNameApp::ExitInstance()  
{  
    return CWinApp::ExitInstance();

}  
```  
  
 Можно просмотреть класс объекта приложения и его `InitInstance` и `ExitInstance` функций в представлении классов.  
  
## <a name="see-also"></a>См. также  
 [Добавление класса](../../ide/adding-a-class-visual-cpp.md)   
 [Создание проекта библиотеки ATL](../../atl/reference/creating-an-atl-project.md)   
 [Конфигурации проектов ATL по умолчанию](../../atl/reference/default-atl-project-configurations.md)

