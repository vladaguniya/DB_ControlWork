graph TD
  %% ===== Ієрархічна модель: Loc → Dept → Emp(+Mgr) =====

  %% Root
  LOC[Loc]
  LOC --> locno((Locno))
  LOC --> lname((Lname))

  %% Dept (child of Loc)
  LOC --> DEPT[Dept]
  DEPT --> deptno((Deptno))
  DEPT --> dname((Dname))

  %% Emp (child of Dept)
  DEPT --> EMP[Emp]
  EMP --> empno((Empno))
  EMP --> ename((Ename))
  EMP --> job((Job))
  EMP --> hiredate((Hiredate))
  EMP --> sal((Sal))
  EMP --> comm((Comm))

  %% Manager subtree (denormalized snapshot)
  EMP --> MGR[Mgr]
  MGR --> mgr_empno((Empno))
  MGR --> mgr_ename((Ename))
  MGR --> mgr_job((Job))
  MGR --> mgr_hiredate((Hiredate))
  MGR --> mgr_sal((Sal))
  MGR --> mgr_comm((Comm))
