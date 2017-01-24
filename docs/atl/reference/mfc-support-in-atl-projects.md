---
title: "Поддержка MFC в проектах ATL | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.atl.addmfc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "проекты ATL, поддержка MFC"
ms.assetid: f90b4276-cb98-4c11-902c-9ebcfe6f954b
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Поддержка MFC в проектах ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Если выбрана **поддержка MFC** в мастере проекта ATL, проект объявляет приложение как объект \(класс\) приложения MFC.  Проект инициализирует библиотеку MFC и создает класс \(класс *ProjName*\), являющийся производным от [CWinApp](../../mfc/reference/cwinapp-class.md).  
  
 Эта возможность доступна только для неатрибутированных проектов библиотек DLL ATL.  
  
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
  
 Класс объектов приложения и его функции `InitInstance` и `ExitInstance` можно просматривать в представлении классов.  
  
## См. также  
 [Добавление класса](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md)   
 [Создание проекта библиотеки ATL](../../atl/reference/creating-an-atl-project.md)   
 [Конфигурации по умолчанию проекта ATL](../../atl/reference/default-atl-project-configurations.md)