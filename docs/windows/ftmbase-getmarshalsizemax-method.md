---
title: "Метод FtmBase::GetMarshalSizeMax | Microsoft Docs"
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
  - "ftm/Microsoft::WRL::FtmBase::GetMarshalSizeMax"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetMarshalSizeMax - метод"
ms.assetid: b416b1bf-c73e-45d5-abb8-04921c1a0c94
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод FtmBase::GetMarshalSizeMax
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Получите количество байт, задающих верхнюю границу, необходимую для маршалирования заданного указателя интерфейсов в указанном объекте.  
  
## Синтаксис  
  
```  
STDMETHODIMP GetMarshalSizeMax(  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags,  
   __out DWORD *pSize  
) override;  
```  
  
#### Параметры  
 `riid`  
 Ссылка на идентификатор интерфейса для маршалинга.  
  
 `pv`  
 Указатель интерфейса, который следует маршалировать; может иметь значение NULL.  
  
 `dwDestContext`  
 Контекст назначения, в котором указанный интерфейс должен быть демаршалирован.  
  
 Укажите одно или несколько значений перечисления MSHCTX.  
  
 В настоящее время демаршалирование может произойти в другом подразделении текущего процесса \(MSHCTX\_INPROC\) или в другом процессе на том же компьютере, где находится текущий процесс \(MSHCTX\_LOCAL\).  
  
 `pvDestContext`  
 Зарезервировано для будущего использования; должно быть NULL.  
  
 `mshlflags`  
 Флаг указывает, могут ли данные, которые должны быть маршалированы, передаваться обратно в процесс клиента — типичный случай — или быть записаны в глобальную таблицу, где их могут извлечь несколько клиентов.  Укажите одно или несколько значений перечисления MSHLFLAGS.  
  
 `pSize`  
 Когда эта операция будет завершена, указатель на верхнюю границу объема данных должен быть записан в поток маршалинга.  
  
## Возвращаемое значение  
 S\_OK, если операция завершилась удачно; в противном случае E\_FAIL или E\_NOINTERFACE.  
  
## Требования  
 **Заголовок:** ftm.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс FtmBase](../windows/ftmbase-class.md)