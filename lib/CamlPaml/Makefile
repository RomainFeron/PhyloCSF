LIBNAME = CamlPaml

lib:
	ocamlbuild -cflag '-unsafe-string' -use-ocamlfind ${LIBNAME}.cma ${LIBNAME}.cmxa

test:
	ocamlbuild -cflag '-unsafe-string' -use-ocamlfind test.native
	_build/test.native


install: lib
	ocamlfind install ${LIBNAME} META _build/${LIBNAME}.cmi _build/${LIBNAME}.cma _build/${LIBNAME}.cmxa _build/${LIBNAME}.a

uninstall:
	ocamlfind remove ${LIBNAME}

reinstall:
	make uninstall
	make install

clean:
	rm -f *~
	ocamlbuild -cflag '-unsafe-string' -clean

doc:
	ocamlbuild -cflag '-unsafe-string' -use-ocamlfind ${LIBNAME}.docdir/index.html
