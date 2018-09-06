---
title: Поддержка MFC в проектах ATL | Документация Майкрософт
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
ms.openlocfilehash: bb6a3c5bae4d973ba74155ab018ebea69b0e2b93
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751404"
---
# <a name="mfc-support-in-atl-projects"></a>Поддержка MFC в проектах ATL

При выборе **поддержки MFC** в мастер проектов ATL, проект объявляет приложение как объект приложения MFC (класс). Проект инициализирует библиотеку MFC и создает класс (класс *ProjName*), производный от [CWinApp](../../mfc/reference/cwinapp-class.md).

Этот параметр доступен без атрибутов ATL DLL только для проектов.

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
[Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)   
[Конфигурации проектов ATL по умолчанию](../../atl/reference/default-atl-project-configurations.md)

