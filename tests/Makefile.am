noinst_PROGRAMS += test-libmongoc


TEST_PROGS = test-libmongoc


TEST_CFLAGS = $(MAINTAINER_CFLAGS) \
	-Wno-format-nonliteral \
	-Wno-deprecated-declarations \
	-DMONGOC_COMPILATION \
	$(BSON_CFLAGS) \
	$(SSL_CFLAGS) \
	$(ZLIB_CFLAGS) \
	$(SASL_CFLAGS) \
	-I$(top_srcdir)/tests \
	-I$(top_srcdir)/src/mongoc \
	-I$(top_builddir)/src/mongoc \
	$(CPPFLAGS) \
	-DBINARY_DIR="\"$(top_srcdir)/tests/binary\"" \
	-DJSON_DIR="\"$(top_srcdir)/tests/json\"" \
	-DBSON_BINARY_DIR="\"$(top_srcdir)/src/libbson/tests/binary\"" \
	-DBSON_JSON_DIR="\"$(top_srcdir)/src/libbson/tests/json\"" \
	-DCERT_TEST_DIR="\"$(top_srcdir)/tests/x509gen\"" \
	-DOS_RELEASE_FILE_DIR="\"$(top_srcdir)/tests/release_files\""

if OS_SOLARIS
TEST_CFLAGS += -D_REENTRANT
endif



TEST_LIBS = \
	$(COVERAGE_LDFLAGS) \
	$(PTHREAD_LIBS) \
	$(SHM_LIB) \
	$(SASL_LIBS) \
	$(RESOLV_LIBS) \
	$(SNAPPY_LIBS) \
	$(ZLIB_LIBRARIES) \
	$(SSL_LIBS)

if EXPLICIT_LIBS
TEST_LIBS += $(BSON_LIBS)
endif
if OS_WIN32
TEST_LIBS += -lshlwapi
endif

test_libmongoc_SOURCES = \
	src/libbson/tests/corpus-test.c \
	src/libbson/tests/corpus-test.h \
	src/libbson/tests/test-atomic.c \
	src/libbson/tests/test-bson.c \
	src/libbson/tests/test-bson-corpus.c \
	src/libbson/tests/test-bson-error.c \
	src/libbson/tests/test-bson-version.c \
	src/libbson/tests/test-endian.c \
	src/libbson/tests/test-clock.c \
	src/libbson/tests/test-decimal128.c \
	src/libbson/tests/test-iso8601.c \
	src/libbson/tests/test-iter.c \
	src/libbson/tests/test-json.c \
	src/libbson/tests/test-oid.c \
	src/libbson/tests/test-reader.c \
	src/libbson/tests/test-string.c \
	src/libbson/tests/test-utf8.c \
	src/libbson/tests/test-value.c \
	src/libbson/tests/test-writer.c \
	src/libbson/tests/test-bcon-basic.c \
	src/libbson/tests/test-bcon-extract.c \
	tests/debug-stream.c \
	tests/json-test.c \
	tests/json-test.h \
	tests/mock_server/future.c \
	tests/mock_server/future.h \
	tests/mock_server/future-functions.c \
	tests/mock_server/future-functions.h \
	tests/mock_server/future-value.c \
	tests/mock_server/future-value.h \
	tests/mock_server/mock-server.c \
	tests/mock_server/mock-server.h \
	tests/mock_server/mock-rs.c \
	tests/mock_server/mock-rs.h \
	tests/mock_server/request.c \
	tests/mock_server/request.h \
	tests/mock_server/sync-queue.c \
	tests/mock_server/sync-queue.h \
	tests/test-libmongoc.c \
	tests/test-conveniences.c \
	tests/test-conveniences.h \
	tests/test-happy-eyeballs.c \
	tests/test-mongoc-array.c \
	tests/test-mongoc-async.c \
	tests/test-mongoc-buffer.c \
	tests/test-mongoc-bulk.c \
	tests/test-mongoc-change-stream.c \
	tests/test-mongoc-client.c \
	tests/test-mongoc-client-pool.c \
	tests/test-mongoc-cluster.c \
	tests/test-mongoc-collection.c \
	tests/test-mongoc-collection-find.c \
	tests/test-mongoc-collection-find-with-opts.c \
	tests/test-mongoc-connection-uri.c \
	tests/test-mongoc-command-monitoring.c \
	tests/test-mongoc-counters.c \
	tests/test-mongoc-cursor.c \
	tests/test-mongoc-database.c \
	tests/test-mongoc-error.c \
	tests/test-mongoc-exhaust.c \
	tests/test-mongoc-find-and-modify.c \
	tests/test-mongoc-gridfs.c \
	tests/test-mongoc-gridfs-file-page.c \
	tests/test-mongoc-handshake.c \
	tests/test-mongoc-log.c \
	tests/test-mongoc-linux-distro-scanner.c \
	tests/test-mongoc-list.c \
	tests/test-mongoc-matcher.c \
	tests/test-mongoc-max-staleness.c \
	tests/test-mongoc-queue.c \
	tests/test-mongoc-read-concern.c \
	tests/test-mongoc-read-write-concern.c \
	tests/test-mongoc-read-prefs.c \
	tests/test-mongoc-retryable-writes.c \
	tests/test-mongoc-rpc.c \
	tests/test-mongoc-socket.c \
	tests/test-mongoc-sample-commands.c \
	tests/test-mongoc-scram.c \
	tests/test-mongoc-sdam.c \
	tests/test-mongoc-sdam-monitoring.c \
	tests/test-mongoc-server-selection.c \
	tests/test-mongoc-server-selection-errors.c \
	tests/test-mongoc-client-session.c \
	tests/test-mongoc-set.c \
	tests/test-mongoc-dns.c \
	tests/test-mongoc-stream.c \
	tests/test-mongoc-thread.c \
	tests/test-mongoc-topology-reconcile.c \
	tests/test-mongoc-topology-scanner.c \
	tests/test-mongoc-topology.c \
	tests/test-mongoc-topology-description.c \
	tests/test-mongoc-uri.c \
	tests/test-mongoc-usleep.c \
	tests/test-mongoc-util.c \
	tests/test-mongoc-version.c \
	tests/test-mongoc-write-commands.c \
	tests/test-mongoc-write-concern.c \
	tests/test-libmongoc.h \
	tests/TestSuite.c \
	tests/TestSuite.h

if ENABLE_SSL
test_libmongoc_SOURCES += \
	tests/test-mongoc-x509.c \
	tests/test-mongoc-stream-tls.c \
	tests/test-mongoc-stream-tls-error.c \
	tests/ssl-test.c \
	tests/ssl-test.h
endif

if ENABLE_SASL_CYRUS
test_libmongoc_SOURCES += \
	tests/test-mongoc-cyrus.c
endif
test_libmongoc_CFLAGS = $(TEST_CFLAGS)
test_libmongoc_LDADD = libmongoc.la \
					   src/libbson/.libs/libbson.la \
					   $(TEST_LIBS)
test_libmongoc_LDFLAGS = -no-undefined \
                         -rpath $(libdir)

noinst_PROGRAMS += test-mongoc-gssapi
test_mongoc_gssapi_SOURCES = tests/test-mongoc-gssapi.c
test_mongoc_gssapi_CFLAGS = $(TEST_CFLAGS)
test_mongoc_gssapi_LDADD = libmongoc.la $(TEST_LIBS)
test_mongoc_gssapi_LDFLAGS = -no-undefined \
                             -rpath $(libdir)

check: test

TEST_ARGS = "--no-fork"

test:
	./test-libmongoc $(TEST_ARGS) -F test-results.json

valgrind: test-libmongoc
	MONGOC_TEST_VALGRIND=on $(LIBTOOL) --mode=execute valgrind --error-exitcode=1 --leak-check=full --gen-suppressions=all --num-callers=32 --suppressions=$(srcdir)/valgrind.suppressions ./test-libmongoc --no-fork $(TEST_ARGS)

local-check: test-libmongoc
	@ export MONGOC_TEST_SKIP_LIVE=on
	./test-libmongoc $(TEST_ARGS) -F test-results.json


DISTCLEANFILES += \
	test-results.json

.PHONY: valgrind debug

EXTRA_DIST += \
	tests/CMakeLists.txt \
	tests/binary/delete1.dat \
	tests/binary/empty.dat \
	tests/binary/get_more1.dat \
	tests/binary/gridfs.dat \
	tests/binary/gridfs-large.dat \
	tests/binary/insert1.dat \
	tests/binary/kill_cursors1.dat \
	tests/binary/msg1.dat \
	tests/binary/query1.dat \
	tests/binary/query2.dat \
	tests/binary/reply1.dat \
	tests/binary/reply2.dat \
	tests/binary/update1.dat \
	tests/mock_server/future-value.h \
	tests/mock_server/future.c \
	tests/mock_server/future.h \
	tests/mock_server/mock-server.c \
	tests/mock_server/mock-server.h \
	tests/mock_server/mock-rs.c \
	tests/mock_server/mock-rs.h \
	tests/mock_server/request.c \
	tests/mock_server/request.h \
	tests/mock_server/sync-queue.c \
	tests/mock_server/sync-queue.h \
	tests/x509gen/7750279a.0 \
	$(wildcard tests/x509gen/*.pem) \
	$(wildcard tests/release_files/*.txt) \
	$(wildcard tests/json/auth/*.json) \
	$(wildcard tests/json/connection_uri/*.json) \
	$(wildcard tests/json/command_monitoring/*.json) \
	$(wildcard tests/json/initial_dns_auth/*.json) \
	$(wildcard tests/json/initial_dns_seedlist_discovery/*.json) \
	$(wildcard tests/json/read_write_concern/*/*.json) \
	$(wildcard tests/json/retryable_writes/*.json) \
	$(wildcard tests/json/server_discovery_and_monitoring/*/*.json) \
	$(wildcard tests/json/server_selection/rtt/*.json) \
	$(wildcard tests/json/server_selection/server_selection/*/*/*.json) \
	$(wildcard tests/json/srv/*.json) \
	$(wildcard tests/json/max_staleness/*/*.json) \
	$(wildcard src/libbson/tests/binary/*.bson) \
	$(wildcard src/libbson/tests/json//*.json) \
	$(wildcard src/libbson/tests/json/bson_corpus/*.json)

if OS_DARWIN
DEBUGGER = lldb --
else
DEBUGGER = gdb --args
endif

debug: test-libmongoc
	$(LIBTOOL) --mode=execute $(DEBUGGER) test-libmongoc $(TEST_ARGS) --no-fork
