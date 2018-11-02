---
title: Поддержка MFC в проектах ATL
ms.date: 11/04/2016
f1_keywords:
- vc.atl.addmfc
helpviewer_keywords:
- ATL projects, MFC support
ms.assetid: f90b4276-cb98-4c11-902c-9ebcfe6f954b
ms.openlocfilehash: 21e3305ce2d2968a3809793eb487317e224351f4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50489392"
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

[Добавление класса](../../ide/adding-a-class-visual-cpp.md)<br/>
[Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)<br/>
[Конфигурации проектов ATL по умолчанию](../../atl/reference/default-atl-project-configurations.md)

