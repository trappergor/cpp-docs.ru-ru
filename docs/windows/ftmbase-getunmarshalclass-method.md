---
title: "Метод FtmBase::GetUnmarshalClass | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ftm/Microsoft::WRL::FtmBase::GetUnmarshalClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetUnmarshalClass - метод"
ms.assetid: 535fc539-5b97-4967-b158-f7568f13d341
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Метод FtmBase::GetUnmarshalClass
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Получает CLSID, который модель COM использует для поиска библиотеки DLL, содержащей код для соответствующей прокси.  Модель COM загружает эту библиотеку DLL для создания неинициализированного экземпляра прокси\-сервера.  
  
## Синтаксис  
  
```  
STDMETHODIMP GetUnmarshalClass(  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags,  
   __out CLSID *pCid  
) override;  
```  
  
#### Параметры  
 `riid`  
 Ссылка на идентификатор интерфейса для маршалинга.  
  
 `pv`  
 Указатель на интерфейс, который следует маршалировать; может иметь значение NULL, если вызывающий объект не имеет указателя на требуемый интерфейс.  
  
 `dwDestContext`  
 Контекст назначения, в котором указанный интерфейс должен быть демаршалирован.  
  
 Укажите одно или несколько значений перечисления MSHCTX.  
  
 Демаршалирование может произойти в другом подразделении текущего процесса \(MSHCTX\_INPROC\) или в другом процессе на том же компьютере, где находится текущий процесс \(MSHCTX\_LOCAL\).  
  
 `pvDestContext`  
 Зарезервировано для будущего использования; должно быть NULL.  
  
 `mshlflags`  
 Когда эта операция завершится, указатель на CLSID должен использоваться для создания прокси в процессе клиента.  
  
 `pCid`  
  
## Возвращаемое значение  
 Возвращает значение S\_OK в случае успешного выполнения; в противном случае возвращает значение S\_FALSE.  
  
## Требования  
 **Заголовок:** ftm.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс FtmBase](../windows/ftmbase-class.md)