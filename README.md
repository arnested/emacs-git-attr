[![MELPA Stable](https://stable.melpa.org/packages/git-attr-badge.svg)](https://stable.melpa.org/#/git-attr)
[![MELPA](https://melpa.org/packages/git-attr-badge.svg)](https://melpa.org/#/git-attr)

# Expose gitattributes to emacs buffers

This tool will let you use [git attributes](https://git-scm.com/docs/gitattributes) in Emacs buffers.

In example the following will get the value of a `foo` git attribute for the file associated with the current buffer:

```elisp
(git-attr-get "foo")
```

The `git-attr-get` function will return

* `t` for git attributes with the value "set"
* `nil` for git attributes with the value "unset"
* `'undecided` for git attributes that are "unspecified"
* and the value itself if the git attribute is set to a value

## git-attr-linguist

The `git-attr-linguist` library adds some functions for the git attributes [`linguist-generated`](https://github.com/github/linguist#generated-code) and [`linguist-vendored`](https://github.com/github/linguist#vendored-code).

It adds a `find-file-hook` and upon visiting a file puts the buffer into `git-attr-linguist-generated-mode` and/or `git-attr-linguist-vendored-mode` minor modes.

Both minor modes just puts the buffer into `read-only-mode`.
