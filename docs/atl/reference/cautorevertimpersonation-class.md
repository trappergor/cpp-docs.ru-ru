---
title: "CAutoRevertImpersonation Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAutoRevertImpersonation"
  - "CAutoRevertImpersonation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAutoRevertImpersonation class"
ms.assetid: 43732849-1940-4bd4-9d52-7a5698bb8838
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAutoRevertImpersonation Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс [CAccessToken](../Topic/CAccessToken%20Class.md) отменяет изменения объектов в nonimpersonating состоянию, когда он выходит из области.  
  
## Синтаксис  
  
```  
  
class CAutoRevertImpersonation  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAutoRevertImpersonation::CAutoRevertImpersonation](../Topic/CAutoRevertImpersonation::CAutoRevertImpersonation.md)|Создает объект `CAutoRevertImpersonation`|  
|[CAutoRevertImpersonation::~CAutoRevertImpersonation](../Topic/CAutoRevertImpersonation::~CAutoRevertImpersonation.md)|Удаляет объект и отменяет изменения олицетворение маркера доступа.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAutoRevertImpersonation::Attach](../Topic/CAutoRevertImpersonation::Attach.md)|Автоматизирует reversion олицетворения маркера доступа.|  
|[CAutoRevertImpersonation::Detach](../Topic/CAutoRevertImpersonation::Detach.md)|Отменяет автоматический reversion олицетворения.|  
|[CAutoRevertImpersonation::GetAccessToken](../Topic/CAutoRevertImpersonation::GetAccessToken.md)|Извлекает текущую маркера доступа, связанное с этим объектом.|  
  
## Заметки  
 [маркер доступа](http://msdn.microsoft.com/library/windows/desktop/aa374909) объект, описывающий контекст безопасности процесса или потока и выделен к каждому пользователю внесенному в журнал в систему Windows NT 2000 или Windows.  Эти маркеры доступа можно представить с классом `CAccessToken`.  
  
 Иногда бывает необходимо олицетворить маркеры доступа.  Этот класс предоставляется для удобства, но он не выполняет олицетворение маркеров доступа; он выполняет автоматический reversion только к nonimpersonated состояние.  Это происходит потому, что олицетворение токена доступа могут выполняться несколькими различными способами.  
  
 Основные сведения о модели управления доступом в Windows см. в разделе [управление доступом](http://msdn.microsoft.com/library/windows/desktop/aa374860) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Требования  
 **Header:** atlsecurity.h  
  
## См. также  
 [Пример ATLSecurity](../../top/visual-cpp-samples.md)   
 [Access Tokens](http://msdn.microsoft.com/library/windows/desktop/aa374909)   
 [Class Overview](../../atl/atl-class-overview.md)