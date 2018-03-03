---
title: "Метод FtmBase::MarshalInterface | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::MarshalInterface
dev_langs:
- C++
helpviewer_keywords:
- MarshalInterface method
ms.assetid: fc8421b4-06e4-4925-b908-c285fe4790d2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9df1e5d7559b434c1af0f1feff3b73b8141a8865
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ftmbasemarshalinterface-method"></a>Метод FtmBase::MarshalInterface
Записывает в поток данные, необходимые для инициализации прокси-объект в некотором процессе клиента.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
STDMETHODIMP MarshalInterface(  
   __in IStream *pStm,  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags  
) override;  
```  
  
#### <a name="parameters"></a>Параметры  
 `pStm`  
 Указатель на поток, который используется во время маршалинга.  
  
 `riid`  
 Ссылка на идентификатор интерфейса, который необходимо маршалировать. Этот интерфейс должен быть производным от интерфейса IUnknown.  
  
 `pv`  
 Указатель на указатель интерфейса, который необходимо маршалировать; может иметь значение NULL, если вызывающий объект не имеет указатель на нужный интерфейс.  
  
 `dwDestContext`  
 Контекст назначения, где должна быть распаковать указанный интерфейс.  
  
 Укажите одно или несколько значений перечисления MSHCTX.  
  
 Распаковка возможна, в другое подразделение (MSHCTX_INPROC) текущего процесса или в другом процессе на том же компьютере, как текущий процесс (MSHCTX_LOCAL).  
  
 `pvDestContext`  
 Зарезервировано для будущего использования; должно иметь значение нуль.  
  
 `mshlflags`  
 Указывает, является ли данные для маршалинга для передачи обратно в процессе клиента — типичный случай — диска или записываются на глобальной таблицы, где можно получить несколькими клиентами.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK  
 Указатель на интерфейс был успешно маршалинга.  
  
 E_NOINTERFACE  
 Указанный интерфейс не поддерживается.  
  
 STG_E_MEDIUMFULL  
 Поток, заполнен.  
  
 E_FAIL  
 Операция выполнена со сбоем.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ftm.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс FtmBase](../windows/ftmbase-class.md)