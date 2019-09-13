```
(defun skdbg (tags msg &rest args) 
  "wraps debug configuration loading and the debugger itself"
  (if (not *skel-dbg*) 
    (setf *skel-dbg* (rik::make-sk-debugger (def-or-config +dbg-params+) *dbg-output-stream*))
  )
  (apply #'rik::sk-debug `(,*skel-dbg* ,tags ,msg ,@args))
)
```
