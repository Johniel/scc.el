# Switch Cursor Color
dash.el が必要です

## Example

    (add-to-list 'scc-color-detector '(lambda () "green"))

    (require 'tramp)
    (defun get-tramp-hostname ()
      (let ((name (buffer-file-name)))
        (if (and name (tramp-tramp-file-p name))
            (tramp-file-name-real-host (tramp-dissect-file-name name)))))
    (add-to-list 'scc-color-detector '(lambda ()
                                        (let ((hostname (get-tramp-hostname)))
                                          (cond ((member hostname '("AAA" "BBB")) "red")
                                                ((member hostname '("CCC" "DDD"))  "deep sky blue")
                                                (t nil)))))
