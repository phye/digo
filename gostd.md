<div id="table-of-contents">
<h2>Table of Contents</h2>
<div id="text-table-of-contents">
<ul>
<li><a href="#sec-1">1. context</a>
<ul>
<li><a href="#sec-1-1">1.1. context.go</a>
<ul>
<li><a href="#sec-1-1-1">1.1.1. Variables</a></li>
<li><a href="#sec-1-1-2">1.1.2. Types</a></li>
<li><a href="#sec-1-1-3">1.1.3. Functions</a></li>
</ul>
</li>
</ul>
</li>
<li><a href="#sec-2">2. net</a>
<ul>
<li><a href="#sec-2-1">2.1. mac.go&#xa0;&#xa0;&#xa0;<span class="tag"><span class="mac">mac</span></span></a>
<ul>
<li><a href="#sec-2-1-1">2.1.1. Types</a></li>
</ul>
</li>
<li><a href="#sec-2-2">2.2. ip.go</a>
<ul>
<li><a href="#sec-2-2-1">2.2.1. Types</a></li>
<li><a href="#sec-2-2-2">2.2.2. Functions</a></li>
</ul>
</li>
<li><a href="#sec-2-3">2.3. net.go</a>
<ul>
<li><a href="#sec-2-3-1">2.3.1. Types</a></li>
<li><a href="#sec-2-3-2">2.3.2. Variables</a></li>
<li><a href="#sec-2-3-3">2.3.3. Functions</a></li>
</ul>
</li>
<li><a href="#sec-2-4">2.4. fd_unix.go</a>
<ul>
<li><a href="#sec-2-4-1">2.4.1. Types</a></li>
<li><a href="#sec-2-4-2">2.4.2. Functions</a></li>
</ul>
</li>
<li><a href="#sec-2-5">2.5. file.go</a>
<ul>
<li><a href="#sec-2-5-1">2.5.1. Types</a></li>
<li><a href="#sec-2-5-2">2.5.2. Functions</a></li>
</ul>
</li>
<li><a href="#sec-2-6">2.6. file_unix.go</a>
<ul>
<li><a href="#sec-2-6-1">2.6.1. Functions</a></li>
</ul>
</li>
<li><a href="#sec-2-7">2.7. sock_posix.go</a>
<ul>
<li><a href="#sec-2-7-1">2.7.1. Types</a></li>
<li><a href="#sec-2-7-2">2.7.2. Functions</a></li>
</ul>
</li>
<li><a href="#sec-2-8">2.8. ipsock.go</a>
<ul>
<li><a href="#sec-2-8-1">2.8.1. Types</a></li>
<li><a href="#sec-2-8-2">2.8.2. Functions</a></li>
</ul>
</li>
<li><a href="#sec-2-9">2.9. ipsock_posix.go</a>
<ul>
<li><a href="#sec-2-9-1">2.9.1. Types</a></li>
<li><a href="#sec-2-9-2">2.9.2. Functions</a></li>
</ul>
</li>
<li><a href="#sec-2-10">2.10. rawconn.go</a>
<ul>
<li><a href="#sec-2-10-1">2.10.1. Types</a></li>
<li><a href="#sec-2-10-2">2.10.2. Functions</a></li>
</ul>
</li>
<li><a href="#sec-2-11">2.11. iprawsock.go</a>
<ul>
<li><a href="#sec-2-11-1">2.11.1. Types</a></li>
<li><a href="#sec-2-11-2">2.11.2. Functions</a></li>
</ul>
</li>
<li><a href="#sec-2-12">2.12. tcpsock.go</a>
<ul>
<li><a href="#sec-2-12-1">2.12.1. Types</a></li>
<li><a href="#sec-2-12-2">2.12.2. Functions</a></li>
</ul>
</li>
<li><a href="#sec-2-13">2.13. tcpsock_posix.go</a>
<ul>
<li><a href="#sec-2-13-1">2.13.1. Types</a></li>
<li><a href="#sec-2-13-2">2.13.2. Functions</a></li>
</ul>
</li>
<li><a href="#sec-2-14">2.14. lookup.go</a>
<ul>
<li><a href="#sec-2-14-1">2.14.1. Variables</a></li>
<li><a href="#sec-2-14-2">2.14.2. Types</a></li>
<li><a href="#sec-2-14-3">2.14.3. Functions</a></li>
</ul>
</li>
<li><a href="#sec-2-15">2.15. <span class="todo TODO">TODO</span> lookup_unix.go</a>
<ul>
<li><a href="#sec-2-15-1">2.15.1. Variables</a></li>
<li><a href="#sec-2-15-2">2.15.2. Types</a></li>
<li><a href="#sec-2-15-3">2.15.3. Functions</a></li>
</ul>
</li>
<li><a href="#sec-2-16">2.16. <span class="todo TODO">TODO</span> dial.go</a>
<ul>
<li><a href="#sec-2-16-1">2.16.1. Types</a></li>
<li><a href="#sec-2-16-2">2.16.2. Functions</a></li>
</ul>
</li>
</ul>
</li>
<li><a href="#sec-3">3. internal</a>
<ul>
<li><a href="#sec-3-1">3.1. poll</a>
<ul>
<li><a href="#sec-3-1-1">3.1.1. fd.go</a></li>
<li><a href="#sec-3-1-2">3.1.2. fd_poll_runtime.go</a></li>
<li><a href="#sec-3-1-3">3.1.3. fd_mutex.go</a></li>
<li><a href="#sec-3-1-4">3.1.4. fd_unix.go</a></li>
</ul>
</li>
</ul>
</li>
</ul>
</div>
</div>


# context<a id="sec-1" name="sec-1"></a>

`Context` type carries deadlines, cancelation signals, and other
request-scoped values across API boundaries and between processes. 

## context.go<a id="sec-1-1" name="sec-1-1"></a>

### Variables<a id="sec-1-1-1" name="sec-1-1-1"></a>

1.  [Canceled](file:///usr/local/go/src/context/context.go)

    The error returned by `Context.Err` when the context is canceled

2.  [DeadlineExceeded](file:///usr/local/go/src/context/context.go)

    The error returned by `Context.Err` when the context's deadline passes

3.  [todo = new(emptyCtx)](file:///usr/local/go/src/context/context.go)

    The internal non-nil, empty Context

4.  [background = new(emptyCtx)](file:///usr/local/go/src/context/context.go)

    The internal non-nil, empty Context named backgroud

### Types<a id="sec-1-1-2" name="sec-1-1-2"></a>

1.  [type emptyCtx int](file:///usr/local/go/src/context/context.go)

    An emptyCtx is never canceled, has no values, and has no deadline. Note that
    it is not struct{}, since vars of this type **must** have distinct addresses. 
    
    emptyCtx implements the following (empty) methods required by Context
    
    [func (\*emptyCtx) Deadline() (deadline time.Time, ok bool) {](file:///usr/local/go/src/context/context.go)
    [func (\*emptyCtx) Done() <-chan struct{} {](file:///usr/local/go/src/context/context.go)
    [func (\*emptyCtx) Err() error {](file:///usr/local/go/src/context/context.go)
    [func (\*emptyCtx) Value(key interface{}) interface{} {](file:///usr/local/go/src/context/context.go)

2.  [type canceler interface {](file:///usr/local/go/src/context/context.go)

        type canceler interface {
            cancel(removeFromParent bool, err error)
            Done() <- chan struct{}
        }
    
    A canceler is a context type that can be canceled directly. The
    implementations are `*cancelCtx` and `*timerCtx`

3.  [type cancelCtx struct {](file:///usr/local/go/src/context/context.go)

        type cancelCtx struct {
            Context                     // Note that, cancelCtx is a struct, not interface :)
        
            mu sync.Mutex
            done chan struct{}
            children map[canceler]struct{}
            err error
        }
    
    1.  [func (c \*cancelCtx) Done() <-chan struct{} {](file:///usr/local/go/src/context/context.go)
    
        **atomically** make a `chan struct{}` and return it. Note that calling
        `cancelCtx.Done` will override `cancelCtx.Context.Done`. 
    
    2.  [func (c \*cancelCtx) Err() error {](file:///usr/local/go/src/context/context.go)
    
        **atomically** return c.err. Also override `cnacelCtx.Context.Err` 
    
    3.  Puzzles
    
        Why `Deadline()` and `Value()` are not implemented? 
        Since they're implemented in `canCtx.Context`. 
        
        Note that cancelCtx is a struct, not an interface :) Thus the
        corresponding methods in `canCtx.Context` is sufficient.
    
    4.  [func (c \*cancelCtx) cancel(removeFromParent bool, err error) {](file:///usr/local/go/src/context/context.go)
    
        **Atomically** closes c.done, then cancels each of c's children. And if
        `removeFromParent` is true, removes c from its parent's `children` map

4.  [type timerCtx struct {](file:///usr/local/go/src/context/context.go)

        type timerCtx struct {
            cancelCtx
            timer *time.Timer // Under cancelCtx.mu.
        
            deadline time.Time
        }
    
    A timerCtx **contains** a cancelCtx (which evetually contains a Context), but
    overrides the `Context`'s Deadline() method
    
    1.  [/usr/local/go/src/context/context.go::func (c \*timerCtx) Deadline() (deadline time.Time, ok bool) {](file:///usr/local/go/src/context/context.go)
    
        Simpler getter to return deadline
    
    2.  [func (c \*timerCtx) cancel(removeFromParent bool, err error) {](file:///usr/local/go/src/context/context.go)
    
        Cancel the timerCtx and stop the timer
        -   Cancel the inner cancelCtx first
        -   Then, remove the context itself from the parent cancelCtx if
            `removeFromParent` is true
        -   Lastly, stop timer atomically

5.  [type valueCtx struct {](file:///usr/local/go/src/context/context.go)

        type valueCtx struct {
            Context
            key, val interface{}
        }
    
    1.  [func (c \*valueCtx) Value(key interface{}) interface{} {](file:///usr/local/go/src/context/context.go)
    
        Return value that matches with key

6.  [type Context interface {](file:///usr/local/go/src/context/context.go)

        type Context interface {
            Deadline() (deadline time.Time, ok bool)
            Done() <-chan struct{}
            Err() error
            Value(key interface{}) interface{}
        }
    
    `Deadline` returns the time when work done on behalf of this context
    should be canceled. `Deadline` returns ok==false when no deadline is
    set. Successive calls to `Deadline` return the same results. 
    
    `Done` returns a channel that's closed when work don on behalf of this
    context should be canceled. Done may return nil if this context can never be
    canceled. Successive calls to Done return the same value.
    
    If `Done` is not yet closed, `Err` returns nil. If `Done` is closed, `Err`
    returns a non-nil error explaining why: 
    
    -   Canceled if the context was canceled
    -   DeadlineExceeded if the context's deadline passed
    
    `Value` returns the value associated with this context for key, or nil if no
    value is associated with key. A key identifies a specific value in a
    Context. **A key can be any type that supports equality.**

7.  [type CancelFunc func()](file:///usr/local/go/src/context/context.go)

    A CancelFunc tells an operation to abandon its work. After the first call,
    subsequent calls to a CancelFunc do nothing

### Functions<a id="sec-1-1-3" name="sec-1-1-3"></a>

1.  [func removeChild(parent Context, child canceler) {](file:///usr/local/go/src/context/context.go)

    Remove `child` from `parent` context

2.  [func newCancelCtx(parent Context) cancelCtx {](file:///usr/local/go/src/context/context.go)

    Return a new `cancelCtx` where `parent` is passed as the `Context` 

3.  [func parentCancelCtx(parent Context) (\*cancelCtx, bool) {](file:///usr/local/go/src/context/context.go)

    Follows a chain of parent references until it finds a \*cancelCtx. This
    function iterate over all the concrete `Context` types in the `context`
    package

4.  [func propagateCancel(parent Context, child canceler) {](file:///usr/local/go/src/context/context.go)

    Summary: Arranges for child to be canceled when parent is. 
    1.  If parent will never be canceled, return directly
    
    2.  Otherwise, try to find the **nearest** parent `cancelCtx`
        -   If such one is found
            -   Already canceled? 
                cancel child directly
            -   Not canceled yet
                Insert child into parent `cancelCtx`'s *children* map **atomically**
        -   Otherwise, do not have a parent cancelCtx
            Start a go routine to wait on parent's cancel channel and child's
            cancel channel
            -   If parent is canceled, continue to cancel child
            -   If child is canceld, nothing to do

5.  [func Background() Context {](file:///usr/local/go/src/context/context.go)

    Return the internal background empty Context

6.  [func TODO() Context {](file:///usr/local/go/src/context/context.go)

    Return the internal todo empty Context

7.  [func WithCancel(parent Context) (ctx Context, cancel CancelFunc) {](file:///usr/local/go/src/context/context.go)

    WithCancel returns a copy of parent with a new Done channel. The returned
    context's Done channel is closed when the returned cancel function is
    called or when the parent context's Done channel is closed, whichever
    happens first. 

8.  [func WithDeadline(parent Context, d time.Time) (Context, CancelFunc) {](file:///usr/local/go/src/context/context.go)

    Summary: Returns a copy of the parent context with the deadline adjusted to
    be no later than d. The returned context's Done channel is closed **1)** when
    the deadline expires, **2)** when the returned cancel function is called, or
    **3)** when the parent context's Done channel is closed, whichever happens
    first.  
    
    -   check if the parent's deadline is before myself; if yes, return
        cancelCtx with parent
    -   Otherwise, create a new timerCtx with a new cancelCtx after parent and
        the deadline `d`
    -   Then, insert the new timerCtx into parent's children map
    -   Then, check if the timer already expires
        -   If yes 
            -   cancel the newly created timerCtx directly
            -   return the newly created timerCtx
        -   Otherwise,
            -   start a timer **atomically** with a callback to cancel the timerCtx
                after timer expires
            -   Lastly, return the timerCtx and a new CancelFunc

9.  [func WithTimeout(parent Context, timeout time.Duration) (Context, CancelFunc) {](file:///usr/local/go/src/context/context.go)

    Simple wrapper over WithDeadline for easy use

10. [func WithValue(parent Context, key, val interface{}) Context {](file:///usr/local/go/src/context/context.go)

    Return a new ValueCtx with key and val set. Note that `key` must be
    comparable and should not be of type string or other built-in type to avoid
    collisions between packages using context. 

# net<a id="sec-2" name="sec-2"></a>

## mac.go     :mac:<a id="sec-2-1" name="sec-2-1"></a>

### Types<a id="sec-2-1-1" name="sec-2-1-1"></a>

1.  [HardwareAddr](file:///usr/local/go/src/net/mac.go)

    HardwareAddr represents a physical address
    
    1.  [String()](file:///usr/local/go/src/net/mac.go)
    
        Convert internal physical addr to human readable
    
    2.  [ParseMAC(s string)](file:///usr/local/go/src/net/mac.go)
    
        Convert human readable MAC to internal byte slice based MAC
        Note that normally MAC address are of 6 bytes, however, there're also [8
        bytes](file:///usr/local/go/src/net/mac.go) and [20 bytes](file:///usr/local/go/src/net/mac.go) MAC 

## ip.go<a id="sec-2-2" name="sec-2-2"></a>

### Types<a id="sec-2-2-1" name="sec-2-2-1"></a>

1.  [IP](file:///usr/local/go/src/net/ip.go)     :ip:

    IP is a single IP address, which can either by IPv4 or IPv6. 
    
    1.  [v4InV6Prefix (10 zeros, 2 0xFFs)](file:///usr/local/go/src/net/ip.go)
    
        Note that IPv4 can be converted to IPv6 address by adding a canonical
    
    2.  [func (ip IP) Equal(x IP) bool {](file:///usr/local/go/src/net/ip.go)
    
        Compare if two IP are equal (taking IPv4 and IPv6 comparison into consideration)
    
    3.  [func (ip IP) To4() IP {](file:///usr/local/go/src/net/ip.go)
    
    4.  [func (ip IP) To16() IP {](file:///usr/local/go/src/net/ip.go)
    
        Two utils to convert IP to v4 or v6
    
    5.  [func (ip IP) Mask(mask IPMask) IP {](file:///usr/local/go/src/net/ip.go)
    
        Return the result of masking the IP address ip with mask
    
    6.  [func (ip IP) String() string {](file:///usr/local/go/src/net/ip.go)
    
        Return the string form of the IP address ip:
        -   "<nil>", if ip has length 0
        -   dotted form, for an IPv4 address
        -   colon form: for IPv6
        -   hexadecimal form of IP, without punctuation, if no other cases apply
    
    7.  [func (ip \*IP) MarshalText()](file:///usr/local/go/src/net/ip.go)
    
        Implements the encoding.TextMarshaler interface, **the encoding is the same as
        returned by String**. 
    
    8.  [func (ip \*IP) UnmarshalText(text {}byte) error](file:///usr/local/go/src/net/ip.go)
    
        Implements the encoding.TextUnmarshaler interface, the IP address should be
        in dot form (for v4) or colon form (for v6)

2.  [IPMask](file:///usr/local/go/src/net/ip.go)     :ipmask:

    1.  [func (m IPMask) Size() (ones, bits int) {](file:///usr/local/go/src/net/ip.go)
    
        Return number of leading ones and total bits in the mask
    
    2.  [func (m IPMask) String() string {](file:///usr/local/go/src/net/ip.go)
    
        Return the hexadecimal form of IP, without punctuation

3.  [IPNet](file:///usr/local/go/src/net/ip.go)     :ipnet:

    IPNet represents an IP network with IP and IPMask
    
    1.  [func (n \*IPNet) Contains(ip IP) bool {](file:///usr/local/go/src/net/ip.go)
    
        Returns whether the network includes ip
    
    2.  [func (n \*IPNet) String() string {](file:///usr/local/go/src/net/ip.go)
    
        Returns the CIDR notation of n like "192.0.2.1/24", or "2001:db8::/48". Note
        that if the network is not in the canonical form, it will return mask as
        hexadecimal form without punctuation like "198.51.100.1/c000ff00"

### Functions<a id="sec-2-2-2" name="sec-2-2-2"></a>

1.  [CIDRMask](file:///usr/local/go/src/net/ip.go) returns an IPMask

2.  [func ParseIP(s string) IP {](file:///usr/local/go/src/net/ip.go)

    Parse s as an IP address, returning the result. Support both IPv4 and IPv6.

3.  [func ParseCIDR(s string) (IP, \*IPNet, error) {](file:///usr/local/go/src/net/ip.go)

    Parses s as a CIDR notation IP address and prefix length, returns the IP
    address and the network implied by the IP and prefix length. 

4.  TODO [parseIPv6](file:///usr/local/go/src/net/ip.go)

    Parse IPv6 address

## net.go<a id="sec-2-3" name="sec-2-3"></a>

### Types<a id="sec-2-3-1" name="sec-2-3-1"></a>

1.  [type conn struct {](file:///usr/local/go/src/net/net.go)

    type `conn` is a simple wrapper over netFD, whose *internal* implementation
    is platform dependent. 
    
    `conn` is a `Conn`, with additional two methods for buffer SETTER. 
    
        type conn struct {
            fd *netFD
        }
    
    1.  [func (c \*conn) ok() bool { return c != nil && c.fd != nil }](file:///usr/local/go/src/net/net.go)
    
        Self-Explanatory
    
    2.  [func (c \*conn) Read(b {}byte) (int, error)](file:///usr/local/go/src/net/lookup_unix.go)
    
        Implements the Conn Read method which is done via `conn.fd.Read` 
    
    3.  [func (c \*conn) Write(b {}byte) (int, error)](file:///usr/local/go/src/net/net.go)
    
        Implements the Conn Write method which is done via `conn.fd.Write` 
    
    4.  [func (c \*conn) Close() error {](file:///usr/local/go/src/net/net.go)
    
        Closes the connection (required by `Conn`)
    
    5.  [func (c \*conn) LocalAddr() Addr {](file:///usr/local/go/src/net/net.go)
    
    6.  [func (c \*conn) RemoteAddr() Addr {](file:///usr/local/go/src/net/net.go)
    
        Simple wrappers over `*netFD.fd` fields. Required by `Conn` interface
    
    7.  [func (c \*conn) SetDeadline(t time.Time) error {](file:///usr/local/go/src/net/net.go)
    
    8.  [func (c \*conn) SetReadDeadline(t time.Time) error {](file:///usr/local/go/src/net/net.go)
    
    9.  [func (c \*conn) SetWriteDeadline(t time.Time) error {](file:///usr/local/go/src/net/net.go)
    
        Wrappers over `*netFD.fd.pdf` methods. Required by `Conn` interface
    
    10. [func (c \*conn) SetReadBuffer(bytes int) error {](file:///usr/local/go/src/net/net.go)
    
    11. [func (c \*conn) SetWriteBuffer(bytes int) error {](file:///usr/local/go/src/net/net.go)
    
        Simple Wrapper over `setReadBuffer` and `setWriteBuffer` 
    
    12. [func (c \*conn) File() (f \*os.File, err error) {](file:///usr/local/go/src/net/net.go)
    
        Per comments, **sets the underlying os.File to blocking mode** and returns a
        copy `f`, which is independent of `c`. 
        
        Note that the setting blocking is done in `*netFD.fd.dup()` 

2.  [type Addr interface {](file:///usr/local/go/src/net/net.go)

    An interface that represents a network end point address
    
        type Addr interface {
            Network() string // name of the network (for example, "tcp", "udp")
            String() string  // string form of address (for example, "192.0.2.1:25", "[2001:db8::1]:80")
        }

3.  [type Conn interface {](file:///usr/local/go/src/net/net.go)

    An interface indicating a generic **stream-oriented** network
    connection. Multiple goroutines may invoke methods on a Conn simultaneously 
    
        type Conn interface {
            Read(b []byte) (n int, err error)
            Write(b []byte) (n int, err error)
            Close() error
        
            LocalAddr() Addr
            RemoteAddr() Addr
        
            SetDeadline(t time.Time) error
            SetReadDeadline(t time.Time) error
            SetWriteDeadline(t time.Time) error
        }
    
    A Conn's interface can be divided into three parts:
    -   IO related,
    -   Address info related
    -   Timeout related

4.  [type PacketCone interface {](file:///usr/local/go/src/net/net.go)

    A generic packet-oriented network connection. Multiple goroutines may
    invoke methods on a PacketConn simultaneously  
    
        type PacketConn interface {
            ReadFrom(b []byte) (n int, addr Addr, err error)
            WriteTo(b []byte, addr Addr) (n int, err error)
            Close() error
        
            LocalAddr() Addr
        
            SetDeadline(t time.Time) error
            SetReadDeadline(t time.Time) error
            SetWriteDeadline(t time.Time) error
        }

5.  [type Listener interface {](file:///usr/local/go/src/net/net.go)

    A generic network listener for stream-oriented protocols. Multiple
    goroutines may invoke methods on a Listener simultaneously. 
    
        type Listener interface {
            // Accept waits for and returns the next connection to the listener.
            Accept() (Conn, error)
        
            // Close closes the listener.
            // Any blocked Accept operations will be unblocked and return errors.
            Close() error
        
            // Addr returns the listener's network address.
            Addr() Addr
        }

6.  [type Error interface {](file:///usr/local/go/src/net/net.go)

    Embeds `error` interface with two additional methods: `Timeout` and
    `Temporary` 

7.  [type OpError struct {](file:///usr/local/go/src/net/net.go)

    An error describes the operation, network type, and address of an error. 

8.  [type ParseError struct {](file:///usr/local/go/src/net/net.go)

    Error type of literal network address parsers

9.  [type AddrError struct {](file:///usr/local/go/src/net/net.go)

    Address error

10. [type DNSConfigError struct {](file:///usr/local/go/src/net/net.go)

11. [fype InvalidAddrError string](file:///usr/local/go/src/net/net.go)

12. [type UnknownNetworkError string](file:///usr/local/go/src/net/net.go)

13. [type DNSError struct {](file:///usr/local/go/src/net/net.go)

14. [type buffersWriter interface {](file:///usr/local/go/src/net/net.go)

        type buffersWriter interface {
            writeBuffers(*Buffers) (int64, error)
        }
    
    `buffersWriter` is the **interface** implemented by Conns that support a
    "writev"-like batch write optimization. `writerBuffers` should fully consume
    all chunks from the provided Buffers, else it should report a non-nil
    error. 

15. [type Buffers {}{}byte](file:///usr/local/go/src/net/net.go)

    1.  [func (v \*Buffers) WriteTo(w io.Writer) (n int64, err error) {](file:///usr/local/go/src/net/net.go)
    
        Implements the `WriteTo` method required by `io.WriterTo` which will write
        all bytes to a writer until no more data to write or when an error occurs
    
    2.  [func (v \*Buffers) Read(p {}byte) (n int, err error)](file:///usr/local/go/src/net/net.go)
    
        a simple buffer read method

### Variables<a id="sec-2-3-2" name="sec-2-3-2"></a>

1.  [var listenerBacklog = maxListenerBacklog()](file:///usr/local/go/src/net/net.go)

    On Linux, return parsed info from `/proc/sys/net/core/somaxconn`

2.  [var threadLimit = make(chan struct{}, 500)](file:///usr/local/go/src/net/net.go)

    Limit the number of cgo threads 

3.  DONE Puzzle

    -   State "DONE"       from "TODO"       <span class="timestamp-wrapper"><span class="timestamp">[2018-03-25 Sun 09:34]</span></span>
    
    Why there're two underscore variables ??
    
        var (
            _ io.WriterTo = (*Buffers)(nil)
            _ io.Reader   = (*Buffers)(nil)
        )
    
    Per [effective go](https://golang.org/doc/effective_go.html#blank), the blank identifiers above indicates that **the
    declaration exists only for the type checking, not to create a variable**. 

### Functions<a id="sec-2-3-3" name="sec-2-3-3"></a>

1.  [func acquireThread() {](file:///usr/local/go/src/net/net.go)

    Send message to `threadLimit` chan (which is a buffered chan of 500 slots) 

2.  [func releaseThread() {](file:///usr/local/go/src/net/net.go)

## fd\_unix.go<a id="sec-2-4" name="sec-2-4"></a>

Defines types and functions representing socket-backended open file
descriptors. Note that/http all socket operations are achieved via
methods defined in `internal/poll`

### Types<a id="sec-2-4-1" name="sec-2-4-1"></a>

1.  [type netFD struct {](file:///usr/local/go/src/net/fd_unix.go)

        type netFD struct {
            pfd poll.FD
        
            // immutable until Close
            family      int
            sotype      int
            isConnected bool
            net         string
            laddr       Addr
            raddr       Addr
        }
    
    Read carefully the doc of internal/poll
    
    > Package poll supports non-blocking I/O on file descriptors **with
    > polling**. This supports I/O operations that **block only a goroutine**, not a
    > thread. This is used by the net and os packages. It uses **a poller built
    > into the runtime**, with support from the runtime scheduler. 
    
    1.  [func (fd \*netFD) init() error {](file:///usr/local/go/src/net/fd_unix.go)
    
        Init the FD by calling `fd.pdf.Init(fd.net, true)` to tell runtime netpoll
        to manage the fd
    
    2.  [func (fd \*netFD) setAddr(laddr, raddr Addr) {](file:///usr/local/go/src/net/fd_unix.go)
    
        SETTERs to set local and remote addr.
        Also, set finalizer for the fd via
        [runtime.SetFinalizer(fd, (\*netFD).Close)](file:///usr/local/go/src/net/fd_unix.go)
        So that user of the package does not need to close the FD explicitly
        (i.e., the garbage collector will close it for you) as long as GC find it
        suitable&#x2026; 
    
    3.  [func (fd \*netFD) name() string {](file:///usr/local/go/src/net/fd_unix.go)
    
        Simple function to return name of the fd in the format below:
        
        tcp: <local\_addr>:<local\_port> -> <remote\_addr>:<remote\_port>
    
    4.  [func (fd \*netFD) connect(ctx context.Context, la, ra syscall.Sockaddr) (rsa syscall.Sockaddr, ret error) {](file:///usr/local/go/src/net/fd_unix.go)
    
        Connect to the remote address, 
        
        1.  Call `connectFunc` (Defined in hook\_unix.go, which should be
            syscall.Connect) 
            
            Switch error handdling based on error:
            
            -   `EINPROGRESS`, `EALREADY`, or `EINTR`, do noop and continue
            -   nil or `EISCONN`, 
                Init `fd.pdf` again, and return nil `rsa`
        
        2.  If ctx has Deadline, associate write deadline with fd.pfd
        
        3.  Then, start the *interrupter* goroutine, if this context can be
            canceled. The *interrupter* goroutine waits for the context to be done
            and interrupts the dial (by altering the fd's write deadline, which
            wakes up waitWrite)
        
        4.  Lastly, performing the actual readable blocking wait
            [if err := fd.pfd.WaitWrite(); err != nil {](file:///usr/local/go/src/net/fd_unix.go)
        
        5.  Lastly, if socket is connected successfully, i.e., SO\_ERROR is 0, call
            `syscall.Getpeername` to get the remote peername
    
    5.  [func (fd \*netFD) Close() error {](file:///usr/local/go/src/net/fd_unix.go)
    
        Clear finalizer and close fd. 
        Simply call internal/poll.FD methods to perform action
    
    6.  [func (fd \*netFD) shutdown(how int) error {](file:///usr/local/go/src/net/fd_unix.go)
    
    7.  [func (fd \*netFD) closeRead() error {](file:///usr/local/go/src/net/fd_unix.go)
    
    8.  [func (fd \*netFD) closeWrite() error {](file:///usr/local/go/src/net/fd_unix.go)
    
        Shutown and variants
        Simply call internal/poll.FD methods to perform action
    
    9.  [func (fd \*netFD) Read(p {}byte) (n int, err error)](file:///usr/local/go/src/net/fd_unix.go)
    
    10. [func (fd \*netFD) readFrom(p {}byte) (n int, sa syscall.Sockaddr, err error)](file:///usr/local/go/src/net/fd_unix.go)
    
    11. [func (fd \*netFD) readMsg(p {}byte, oob {}byte) (n, oobn, flags int, sa syscall.Sockaddr, err error)](file:///usr/local/go/src/net/fd_unix.go)
    
        Read and variants
        Simply call internal/poll.FD methods to perform action
    
    12. [func (fd \*netFD) Write(p {}byte) (nn int, err error)](file:///usr/local/go/src/net/fd_unix.go)
    
    13. [func (fd \*netFD) writeTo(p {}byte, sa syscall.Sockaddr) (n int, err error)](file:///usr/local/go/src/net/fd_unix.go)
    
    14. [func (fd \*netFD) writeMsg(p {}byte, oob {}byte, sa syscall.Sockaddr) (n int, oobn int, err error)](file:///usr/local/go/src/net/fd_unix.go)
    
        Write and vairants
        Simply call internal/poll.FD methods to perform action
    
    15. [func (fd \*netFD) accept() (netfd \*netFD, err error) {](file:///usr/local/go/src/net/fd_unix.go)
    
        Call poll.FD.Accept method to accept a new socket connection in *d* 
        
        Then, create a new *netfd* with *d* and fields in *fd* to create a new
        *netfd*, init and setAddr for it
    
    16. [func (fd \*netFD) dup() (f \*os.File, err error) {](file:///usr/local/go/src/net/fd_unix.go)
    
        **fd will be blocking after this function call!**
        
        Duplicate fd with an `*os.File`, note that fd.pfd is set to blocking so
        that both the old fd and new fd are blocking (note that, O\_BLOCKING is a
        field in open file descriptors, hence are shared across dup)
    
    17. [func (fd \*netFD) addrFunc() func(syscall.Sockaddr) Addr {](file:///usr/local/go/src/net/sock_posix.go)
    
        **Defined in sock\_posix.go**
        
        Returns functions to be called to convert `syscall.Sockaddr` interface to
        `net.Addr` interface  
    
    18. [func (fd \*netFD) dial(ctx context.Context, laddr, raddr sockaddr) error {](file:///usr/local/go/src/net/sock_posix.go)
    
        **Defined in sock\_posix.go**
        
        Actually connect to the remote host
        
        1.  Bind local IP if necessary via `syscall.Bind`
        2.  Connect to the rmeote host via `*netFD.connect`
        3.  Lastly, save local addr and remote add to *fd*
    
    19. [func (fd \*netFD) listenStream(laddr sockaddr, backlog int) error {](file:///usr/local/go/src/net/sock_posix.go)
    
        **Defined in sock\_posix.go**
        
        1.  Set default sock opts for Listener,
        2.  Bind local addr if necessary
        3.  Set listen backlog
        4.  Set local addr to *fd*
    
    20. [func (fd \*netFD) listenDatagram(laddr sockaddr) error {](file:///usr/local/go/src/net/sock_posix.go)
    
        **Defined in sock\_posix.go**
        
        1.  Special handling for Muticast UDP Sockets
        2.  Bind local addr if necessary
        3.  Set local addr to *fd*

### Functions<a id="sec-2-4-2" name="sec-2-4-2"></a>

1.  [func newFD(sysfd, family, sotype int, net string) (\*netFD, error) {](file:///usr/local/go/src/net/fd_unix.go)

    *sysfd*: The int FD
    *family*: PF\_INET, PF\_LOCAL, PF\_UNIX .etc
    *sotype*: socket type, i.e., SOCK\_STREAM, SOCK\_DGRAM .etc
    *net*: Network string

## file.go<a id="sec-2-5" name="sec-2-5"></a>

Defines functions for getting *Conn*, *PacketConn*, and *Listner* from an
open file descriptor `*os.File`

### Types<a id="sec-2-5-1" name="sec-2-5-1"></a>

1.  [type fileAddr string](file:///usr/local/go/src/net/file.go)

    1.  [func (fileAddr) Network() string { return "file+net" }](file:///usr/local/go/src/net/file.go)
    
    2.  [func (f fileAddr) String() string { return string(f) }](file:///usr/local/go/src/net/file.go)
    
        Methods requierd by `Addr` interface

### Functions<a id="sec-2-5-2" name="sec-2-5-2"></a>

1.  [func FileConn(f \*os.File) (c Conn, err error) {](file:///usr/local/go/src/net/file.go)

    Return a Conn given an \*os.File (which represents an open file descriptor)
    by wrapping platform dependent `fileConn` function

2.  [func FileListener(f \*os.File) (ln Listener, err error) {](file:///usr/local/go/src/net/file.go)

    Returns a copy of the network listener corresponding to the open file
    descriptor *f*. 

3.  [func FilePacketConn(f \*os.File) (c PacketConn, err error) {](file:///usr/local/go/src/net/file.go)

    Return a copy of the packet network connection corresponding to the open
    file descriptor *f*.

## file\_unix.go<a id="sec-2-6" name="sec-2-6"></a>

Defines the actual logic to convert \*os.File -> \*netFD -> {Conn, Listener and
PacketConn}

### Functions<a id="sec-2-6-1" name="sec-2-6-1"></a>

1.  [func dupSocket(f \*os.File) (int, error) {](file:///usr/local/go/src/net/file_unix.go)

    dup f.FD() with CloseOnExec flag, and set the dupped socket fd as
    **NONBLOCKING** (which will make the f as nonblocking as well)

2.  [func newFileFD(f \*os.File) (\*netFD, error) {](file:///usr/local/go/src/net/file_unix.go)

    Create a new `netFD` and init it
    
    Firstly, dup *f* via `dupSocket` to get a new fd *s* and set the
    NONBLOCKING flag
    
    Then, create a new \*netFD via `newFD`, init it and update other fields per
    info from the open socket *s*

3.  [func fileConn(f \*os.File) (Conn, error) {](file:///usr/local/go/src/net/file_unix.go)

    Given an open file descriptor *f*, return the corresponding `Conn` 
    
    Supported Conns are: TCP, UDP, IP and UDS (Unix Domain Socket)
    
    Firsly, create a new \*netFD *fd* via `newFileFD` 
    Then, return corresponding Conn based on `fd.laddr.(type)` 

4.  [func fileListener(f \*os.File) (Listener, error) {](file:///usr/local/go/src/net/file_unix.go)

    Given an open file descriptor *f*, return the corresponding `Listener`
    
    Supported Listeners: TCP and UDS

5.  [func filePacketConn(f \*os.File) (PacketConn, error) {](file:///usr/local/go/src/net/file_unix.go)

    Given an open file descriptor *f*, return the corresponding `PacketConn` 

## sock\_posix.go<a id="sec-2-7" name="sec-2-7"></a>

### Types<a id="sec-2-7-1" name="sec-2-7-1"></a>

1.  [type sockaddr interface {](file:///usr/local/go/src/net/sock_posix.go)

    `sockaddr` interface adds additional methods to `Addr` interface. Pay
    special attention to `sockaddr` method, which converts the addr into
    `syscall.Sockaddr` 
    
        type sockaddr interface {
            Addr
        
            // family returns the platform-dependent address family
            // identifier.
            family() int
        
            // isWildcard reports whether the address is a wildcard
            // address.
            isWildcard() bool
        
            // sockaddr returns the address converted into a syscall
            // sockaddr type that implements syscall.Sockaddr
            // interface. It returns a nil interface when the address is
            // nil.
            sockaddr(family int) (syscall.Sockaddr, error)
        
            // toLocal maps the zero address to a local system address (127.0.0.1 or ::1)
            toLocal(net string) sockaddr
        }

2.  More methods for \*netFD (noted in \*netFD)

### Functions<a id="sec-2-7-2" name="sec-2-7-2"></a>

1.  [func socket(ctx context.Context, net string, family, sotype, proto int, ipv6only bool, laddr, raddr sockaddr) (fd \*netFD, err error) {](file:///usr/local/go/src/net/sock_posix.go)

    Returns a network file descriptor that is ready for async IO using the
    network poller
    
    Firstly, get a sock FD *s* via `sysSocket` whose SOCK\_CLOEXEC is set
    Then, set default socket options for *s*
    Then, create a new `*netFD` *fd*
    If laddr is nonnil but raddr is, the socket is a Listener
    -   for TCP, set the max listener backlog and bind local addr
    -   For UDP, simply bind the local addr
    
    Otherwise, the socket is a dialer, dial the remote addr

## ipsock.go<a id="sec-2-8" name="sec-2-8"></a>

### Types<a id="sec-2-8-1" name="sec-2-8-1"></a>

1.  [type ipStackCapabilities struct {](file:///usr/local/go/src/net/ipsock.go)

    Reports capabilities of IP stack, such as IPv4, IPv6, IPv4OverIPv6 .etc 

2.  type addrList {}Addr

    Represents a list of network endpoint Addr
    
    1.  [func (addrs addrList) forResolve(network, addr string) Addr {](file:///usr/local/go/src/net/ipsock.go)
    
        Returns the most appropriate address in *address* for a call to
        ResolveTCPAddr, ResolveUDPAddr, or ResolveIPAddr
    
    2.  [func (addrs addrList) first(strategy func(Addr) bool) Addr {](file:///usr/local/go/src/net/ipsock.go)
    
        Returns the first address which satisfies strategy, or if none do, then
        the first address of any kind
        
        Pay special attention to `strategy` which is a function variable
    
    3.  [func (addrs addrList) partition(strategy func(Addr) bool) (primaries, fallbacks addrList) {](file:///usr/local/go/src/net/ipsock.go)

### Functions<a id="sec-2-8-2" name="sec-2-8-2"></a>

1.  [func supportsIPv4() bool {](file:///usr/local/go/src/net/ipsock.go)

2.  [func supportsIPv6() bool {](file:///usr/local/go/src/net/ipsock.go)

3.  [func supportsIPv4map() bool {](file:///usr/local/go/src/net/ipsock.go)

    Simple GETTERs to return members of `ipStackCaps` which will invoke
    platform dependent `ipStackCaps.probe` **once**. 

4.  [func isIPv4(addr Addr) bool {](file:///usr/local/go/src/net/ipsock.go)

    reports whether addr contains an IPv4 address
    **Supported Addrs**: `*TCPAddr`, `*UDPAddr`, `*IPAddr`

5.  [func filterAddrList(filter func(IPAddr) bool, ips {}IPAddr, inetaddr func(IPAddr) Addr, original string) (addrList, error)](file:///usr/local/go/src/net/ipsock.go)

    applies a filter to a list of `IPAddr`, and convert the filtered IPAddrs to
    a slice of Addrs

6.  [func SplitHostPort(hostport string) (host, port string, err error) {](file:///usr/local/go/src/net/ipsock.go)

    Splits a newtwork address of the form "host:port", "host%zone:port",
    "[host]:port", or "[host%zone]:port" into "host" or "host%zone" and "port" 

7.  [func splitHostZone(s string) (host, zone string) {](file:///usr/local/go/src/net/ipsock.go)

8.  [func JoinHostPort(host, port string) string {](file:///usr/local/go/src/net/ipsock.go)

    Self Explanatory

9.  [func loopbackIP(net string) IP {](file:///usr/local/go/src/net/ipsock.go)

    Return an IPv6 or IPv4 loopback IP address

## ipsock\_posix.go<a id="sec-2-9" name="sec-2-9"></a>

### Types<a id="sec-2-9-1" name="sec-2-9-1"></a>

1.  type ipStackCapabilities

    1.  [func (p \*ipStackCapabilities) probe() {](file:///usr/local/go/src/net/ipsock_posix.go)
    
        Probe kernel for IPv4, IPv6 and IPv4-mapped IPv6 capabilities

### Functions<a id="sec-2-9-2" name="sec-2-9-2"></a>

1.  [func favoriteAddrFamily(network string, laddr, raddr sockaddr, mode string) (family int, ipv6only bool) {](file:///usr/local/go/src/net/ipsock_posix.go)

    Return favorite addr family (which is either AF\_INET or AF\_INET6) and
    whether ipv6only

2.  [func internetSocket(ctx context.Context, net string, laddr, raddr sockaddr, sotype, proto int, mode string) (fd \*netFD, err error) {](file:///usr/local/go/src/net/ipsock_posix.go)

    Return \*netFD for network file descriptor
    
    1.  Firstly get the favorite addr family
    2.  Return socket via `net.socket` defined in `sock_posix.go`

3.  [func ipToSockaddr(family int, ip IP, port int, zone string) (syscall.Sockaddr, error) {](file:///usr/local/go/src/net/ipsock_posix.go)

    Convert ip and port into `syscall.Sockaddr`

## rawconn.go<a id="sec-2-10" name="sec-2-10"></a>

### Types<a id="sec-2-10-1" name="sec-2-10-1"></a>

1.  [type rawConn struct {](file:///usr/local/go/src/net/rawconn.go)

        type rawConn struct {
            fd *netFD
        }
    
    1.  [func (c \*rawConn) ok() bool { return c != nil && c.fd != nil }](file:///usr/local/go/src/net/rawconn.go)
    
    2.  [func (c \*rawConn) Control(f func(uintptr)) error {](file:///usr/local/go/src/net/rawconn.go)
    
    3.  [func (c \*rawConn) Read(f func(uintptr) bool) error {](file:///usr/local/go/src/net/rawconn.go)
    
    4.  [func (c \*rawConn) Write(f func(uintptr) bool) error {](file:///usr/local/go/src/net/rawconn.go)
    
        Calls the use-defined function *f* for Control/Read/Write operation. The
        above three methods are required by `syscall.RawConn` interface

2.  [type rawListener struct {](file:///usr/local/go/src/net/rawconn.go)

    Simple wrapper over rawConn
    
        type rawListener struct {
            rawConn
        }

### Functions<a id="sec-2-10-2" name="sec-2-10-2"></a>

1.  [func newRawConn(fd \*netFD) (\*rawConn, error) {](file:///usr/local/go/src/net/rawconn.go)

## iprawsock.go<a id="sec-2-11" name="sec-2-11"></a>

### Types<a id="sec-2-11-1" name="sec-2-11-1"></a>

1.  [type IPAddr struct {](file:///usr/local/go/src/net/iprawsock.go)

        type IPAddr struct {
            IP   IP
            Zone string // IPv6 scoped addressing zone
        }
    
    1.  [func (a \*IPAddr) Network() string { return "ip" }](file:///usr/local/go/src/net/iprawsock.go)
    
        Network() method, required by `Addr`
    
    2.  [func (a \*IPAddr) String() string {](file:///usr/local/go/src/net/iprawsock.go)
    
        String() method, required by `Addr`, returns ip%zone, if zone is not emty 
    
    3.  [func (a \*IPAddr) isWildcard() bool {](file:///usr/local/go/src/net/iprawsock.go)
    
        Return if any IP ddr
    
    4.  [func (a \*IPAddr) opAddr() Addr {](file:///usr/local/go/src/net/iprawsock.go)
    
        Simply convert IPAddr to Addr

2.  [type IPConn struct {](file:///usr/local/go/src/net/iprawsock.go)

    A simple wrapper which embeds `conn` (which implements `net.Conn`
    interface). Note that `IPConn` implements methods required by
    `net.PacketConn` interface
    
        type IPConn struct {
            conn
        }
    
    1.  [func (c \*IPConn) SyscallConn() (syscall.RawConn, error) {](file:///usr/local/go/src/net/iprawsock.go)
    
        Return net.rawConn which satisfies `syscall.RawConn` interface
    
    2.  [func (c \*IPConn) ReadFromIP(b {}byte) (int, \*IPAddr, error)](file:///usr/local/go/src/net/iprawsock.go)
    
    3.  [func (c \*IPConn) ReadFrom(b {}byte) (int, Addr, error)](file:///usr/local/go/src/net/iprawsock.go)
    
    4.  [func (c \*IPConn) ReadMsgIP(b, oob {}byte) (n, oobn, flags int, addr \*IPAddr, err error)](file:///usr/local/go/src/net/iprawsock.go)
    
        Simliar functions which call platform dependent `c.readFrom` to read bytes
        into b and return (# of bytes, addr, error)
    
    5.  [func (c \*IPConn) WriteToIP(b {}byte, addr \*IPAddr) (int, error)](file:///usr/local/go/src/net/iprawsock.go)
    
    6.  [func (c \*IPConn) WriteTo(b {}byte, addr Addr) (int, error)](file:///usr/local/go/src/net/iprawsock.go)
    
    7.  [func (c \*IPConn) WriteMsgIP(b, oob {}byte, addr \*IPAddr) (n, oobn int, err error)](file:///usr/local/go/src/net/iprawsock.go)

### Functions<a id="sec-2-11-2" name="sec-2-11-2"></a>

1.  [func ResolveIPAddr(network, address string) (\*IPAddr, error) {](file:///usr/local/go/src/net/iprawsock.go)

    Returns an address of IP end point

2.  [func newIPConn(fd \*netFD) \*IPConn { return &IPConn{conn{fd}} }](file:///usr/local/go/src/net/iprawsock.go)

    Given `*netFD`, return `*IPConn`

3.  [func DialIP(network string, laddr, raddr \*IPAddr) (\*IPConn, error) {](file:///usr/local/go/src/net/iprawsock.go)

    Acts like Dial for IP networks. The network must be an IP network name. 
    
    Call platform dependent `dialIP` with `Background` context to dial remote
    addr and return `*IPConn`

4.  [func ListenIP(network string, laddr \*IPAddr) (\*IPConn, error) {](file:///usr/local/go/src/net/iprawsock.go)

    Acts like `ListenPacket` for IP networks
    
    Call platform dependent `listenIP` with `Background` context and return
    the `*IPConn` connection

## tcpsock.go<a id="sec-2-12" name="sec-2-12"></a>

### Types<a id="sec-2-12-1" name="sec-2-12-1"></a>

1.  [type TCPAddr struct {](file:///usr/local/go/src/net/tcpsock.go)

    Represents the address of a TCP end point
    
        type TCPAddr struct {
            IP   IP
            Port int
            Zone string // IPv6 scoped addressing zone
        }
    
    1.  [func (a \*TCPAddr) Network() string { return "tcp" }](file:///usr/local/go/src/net/tcpsock.go)
    
    2.  [func (a \*TCPAddr) String() string {](file:///usr/local/go/src/net/tcpsock.go)
    
        Methods required by `Addr` interface
    
    3.  [func (a \*TCPAddr) isWildcard() bool {](file:///usr/local/go/src/net/tcsock.go)
    
    4.  [func (a \*TCPAddr) opAddr() Addr {](file:///usr/local/go/src/net/tcpsock.go)
    
        Aug self explanatory methods
    
    5.  [func (a \*TCPAddr) family() int {](file:///usr/local/go/src/net/tcpsock_posix.go)
    
    6.  [func (a \*TCPAddr) sockaddr(family int) (syscall.Sockaddr, error) {](file:///usr/local/go/src/net/tcpsock_posix.go)
    
    7.  [func (a \*TCPAddr) toLocal(net string) sockaddr {](file:///usr/local/go/src/net/tcpsock_posix.go)
    
        All **Defined in tcp\_sock\_posix.go**

2.  [type TCPConn struct {](file:///usr/local/go/src/net/tcpsock.go)

    Embeds conn struct to "inherit" common methods and overrides certain
    methods 
    
        type TCPConn struct {
            conn
        }
    
    1.  [func (c \*TCPConn) SyscallConn() (syscall.RawConn, error) {](file:///usr/local/go/src/net/tcpsock.go)
    
        Required by `syscall.Conn` interface which returns a `syscall.RawConn`
        interface 
    
    2.  [func (c \*TCPConn) ReadFrom(r io.Reader) (int64, error) {](file:///usr/local/go/src/net/tcpsock.go)
    
        Required by `io.ReaderFrom` interface
        
        Read from reader *r* until EOF or error, returns no. of bytes read on
        success and send out via *c*
    
    3.  [func (c \*TCPConn) CloseRead() error {](file:///usr/local/go/src/net/tcpsock.go)
    
    4.  [func (c \*TCPConn) CloseWrite() error {](file:///usr/local/go/src/net/tcpsock.go)
    
        Shutdown the reading side/writing side of the TCP connection
    
    5.  [func (c \*TCPConn) SetLinger(sec int) error {](file:///usr/local/go/src/net/tcpsock.go)
    
        Sets the behavior of Close on a connection which still has data waiting to
        be sent or to be acked. 
    
    6.  [func (c \*TCPConn) SetNoDelay(noDelay bool) error {](file:///usr/local/go/src/net/tcpsock.go)
    
        Controls whether the system should delay packet transmission in hopes of
        fewer packets. Default is true
    
    7.  [func (c \*TCPConn) SetKeepAlive(keepalive bool) error {](file:///usr/local/go/src/net/tcpsock.go)
    
    8.  [func (c \*TCPConn) SetKeepAlivePeriod(d time.Duration) error {](file:///usr/local/go/src/net/tcpsock.go)
    
        Call platform dependent functions to set keepalive related settings
    
    9.  [func (c \*TCPConn) readFrom(r io.Reader) (int64, error) {](file:///usr/local/go/src/net/tcpsock_posix.go)
    
        Try to call **sendFile** first, if not handled, fallback to
        `genericReadFrom` defined in net.go 
    
    10. [func (ln \*TCPListener) accept() (\*TCPConn, error) {](file:///usr/local/go/src/net/tcpsock_posix.go)
    
    11. [func (ln \*TCPListener) close() error {](file:///usr/local/go/src/net/tcpsock_posix.go)
    
    12. [func (ln \*TCPListener) file() (\*os.File, error) {](file:///usr/local/go/src/net/tcpsock_posix.go)
    
        Call netFD's methods to perform the corresponding actions

3.  [type TCPListener struct {](file:///usr/local/go/src/net/tcpsock.go)

    TCPListner is a TCP network listener. 
    
        type TCPListener struct {
            fd *netFD
        }
    
    1.  [func (l \*TCPListener) SyscallConn() (syscall.RawConn, error) {](file:///usr/local/go/src/net/tcpsock.go)
    
        Required by `syscall.Conn` interface which returns a `syscall.RawConn`
        interface 
    
    2.  [func (l \*TCPListener) AcceptTCP() (\*TCPConn, error) {](file:///usr/local/go/src/net/tcpsock.go)
    
        Accepts the next incoming call and returns the new connection
    
    3.  [func (l \*TCPListener) Accept() (Conn, error) {](file:///usr/local/go/src/net/tcpsock.go)
    
        Similiar with above, but return a generic Conn
    
    4.  [func (l \*TCPListener) Close() error {](file:///usr/local/go/src/net/tcpsock.go)
    
        Stop listening on the TCP address. 
    
    5.  [func (l \*TCPListener) SetDeadline(t time.Time) error {](file:///usr/local/go/src/net/tcpsock.go)
    
        Sets the deadline associated with the listener. Similiar with the methods
        of `struct conn` 
    
    6.  [func (l \*TCPListener) File() (f \*os.File, err error) {](file:///usr/local/go/src/net/tcpsock.go)
    
        Returns a copy of the underlying os.File, set to blocking mode. Similiar
        with that defined in net.go of `struct conn`

### Functions<a id="sec-2-12-2" name="sec-2-12-2"></a>

1.  [func ResolveTCPAddr(network, address string) (\*TCPAddr, error) {](file:///usr/local/go/src/net/tcpsock.go)

    Returns an address of TCP end point by using
    `DefaultResolver.internetAddrList` 

2.  [func ListenTCP(network string, laddr \*TCPAddr) (\*TCPListener, error) {](file:///usr/local/go/src/net/tcpsock.go)

    Given network and local addr, returns a TCPListener 

## tcpsock\_posix.go<a id="sec-2-13" name="sec-2-13"></a>

### Types<a id="sec-2-13-1" name="sec-2-13-1"></a>

### Functions<a id="sec-2-13-2" name="sec-2-13-2"></a>

1.  [func sockaddrToTCP(sa syscall.Sockaddr) Addr {](file:///usr/local/go/src/net/tcpsock_posix.go)

    Convert `syscall.Sockaddr` to `Addr`

2.  [func doDialTCP(ctx context.Context, net string, laddr, raddr \*TCPAddr) (\*TCPConn, error) {](file:///usr/local/go/src/net/tcpsock_posix.go)

    Call internetSocket to actually connect to remote peer and return a
    netFD, then return a `TCPConn` based on `netFD`
    
    Handled TCP 'simultaneous connection' bug properly

3.  [func listenTCP(ctx context.Context, network string, laddr \*TCPAddr) (\*TCPListener, error) {](file:///usr/local/go/src/net/tcpsock_posix.go)

    Call internetSocket to actually start a listen socket and return netFD,
    then return a `TCPListner` based on `netFD`

## lookup.go<a id="sec-2-14" name="sec-2-14"></a>

### Variables<a id="sec-2-14-1" name="sec-2-14-1"></a>

1.  [dnsWaitGroup](file:///usr/local/go/src/net/ip.go)

    A internal wait group to wait for all goroutines to finish

2.  [DefaultResolver](file:///usr/local/go/src/net/lookup.go)

    Default **package-level** Lookup functions and by Dialers without a specified
    Resolver 

### Types<a id="sec-2-14-2" name="sec-2-14-2"></a>

1.  [type Resolver struct {](file:///usr/local/go/src/net/lookup.go)

    A `Resolver` looks up names and numbers. 
    
        type Resolver struct {
            PreferGo bool
            StrictErrors bool
            Dial func(ctx context.Context, network, address string) (Conn, error)
        }
    
    Note that the `Dial` function optionally specifies an alternate dialer for
    use by Go's built-in DNS resolver to make TCP and UDP connections to DNS
    services. 
    
    1.  [func (r \*Resolver) LookupHost(ctx context.Context, host string) (addrs {}string, err error)](file:///usr/local/go/src/net/lookup.go)
    
        Looks up the given host using the local resolver, note that **either IP
        address or hostname is supported** 
        
        If host is IP address, return IP parsed directly. Otherwise, call platform
        specific `r.lookupHost` to actually lookup the host
    
    2.  [func (r \*Resolver) LookupIPAddr(ctx context.Context, host string) ({}IPAddr, error)](file:///usr/local/go/src/net/lookup.go)
    
        Looks up host using the local resolver. **either IP or hostname is
        supported** 
        
        Details:
        -   try to parse host as IP address. If successful, return IP address
            directly
        -   If there're netrace variables in `ctx`, call `trace.DNSStart(host)`
        -   Add 1 in `dnsWaitGroup`, 
            
            [var dnsWaitGroup sync.WaitGroup](file:///usr/local/go/src/net/lookup.go)
        -   Then, start **only** one DNS request via `loookupGroup.DoChan`, which is a
            method defined in `singleflight.Grop`. I.e., however many goroutines
            there're that's trying to make DNS request, **only one** of them will
            actually run, all other goroutines will just wait for the result and use
            it when the result is ready.
            [ch, called := lookupGroup.DoChan(host, func() (interface{}, error) {](file:///usr/local/go/src/net/lookup.go)
        -   Then, blocks at `select` at channel, until either `ctx.Done()` channel
            or result channel `ch` is readable. 
            
            When `ch` is readable, i.e., DNS query returns successfully, returns the
            slice of `IPAddr`. 
            
            When `ctx.Done()` is readable due to deadline exceeded, simply call
            `lookupGroup.Forget(host)` so that further DNS query will continue to
            start instead of wait
    
    3.  [func (r \*Resolver) LookupPort(ctx context.Context, network, service string) (port int, err error) {](file:///usr/local/go/src/net/lookup.go)
    
        Looks up the port for the given network and service
        
        Details:
        -   Try to parse service as a number. 
            -   If `service` is indeed a number, return the port no. directly.
            -   Otherwise, call platform dependent `Resolver.lookupPort` to lookup the
                port no. and return it
    
    4.  Other methods omitted
    
        `LookupCNAME`, `LookupSRV`, `LookupMX`, `LookupNS`, `LookupTXT` are all simple
        wrappers over platform-dependent corresponding logic
        
        Pay special attention to `LookupAddr` method which performs reverse DNS
        lookup. 
    
    5.  [func (r \*Resolver) internetAddrList(ctx context.Context, net, addr string) (addrList, error) {](file:///usr/local/go/src/net/ipsock.go)
    
        **Defined in ipsock.go**
        Resolves *addr*, which may be a literal IP address or a DNS name, and
        returns a list of internet protocol family addresses. 
        
        1.  For TCP and UDP, split addr into host and port. Then lookup port no. via
            `r.LookupPort`. For IP *net*, simply save addr to host
        2.  Then, define an inner function `inetaddr`, which convert an `IPAddr` to
            `Addr`
        3.  Try to convert host to IP address
            -   Parse as IPv4 directly, if error, continue
            -   Parse as IPv6 address, continue on error
            -   Lastly, try to lookup the IP addr via DNS resolve
        4.  Lastly, filter the addr list and returns IPs that's matching *net*

### Functions<a id="sec-2-14-3" name="sec-2-14-3"></a>

1.  [func lookupProtocolMap(name string) (int, error) {](file:///usr/local/go/src/net/lookup.go)

    Given protocol name, return protocol number

2.  [func lookupPortMap(network, service string) (port int, error error) {](file:///usr/local/go/src/net/lookup.go)

    Given network(tcp or udp) and service name(http, https .etc), return the
    corresponding default port number

3.  [func LookupHost(host string) (addrs {}string, err error)](file:///usr/local/go/src/net/lookup.go)

    looks up the given host using the local default resolver. 

4.  [func LookupIP(host string) ({}IP, error)](file:///usr/local/go/src/net/lookup.go)

    Looks up the given host's IP addresses 

5.  [func LookupPort(network, service string) (port int, err error) {](file:///usr/local/go/src/net/lookup.go)

    Given network and service, return the port no. 
    
    A simple wrapper of `Resolver.LookupPort` 
    
    Note that the Port lookup uses `Background` context which will never be
    canceled. 
    [return DefaultResolver.LookupPort(context.Background(), network, service)](file:///usr/local/go/src/net/lookup.go)

6.  Other simple functions omitted

## TODO lookup\_unix.go<a id="sec-2-15" name="sec-2-15"></a>

### Variables<a id="sec-2-15-1" name="sec-2-15-1"></a>

1.  [var onceReadProtocols sync.Once](file:///usr/local/go/src/net/lookup_unix.go)

    `sync.Once` variable to protect `readProtocols` function below

### Types<a id="sec-2-15-2" name="sec-2-15-2"></a>

### Functions<a id="sec-2-15-3" name="sec-2-15-3"></a>

1.  [func readProtocols() {](file:///usr/local/go/src/net/lookup_unix.go)

    Read "/etc/protocols" into memory and store the protocol results in
    net.protocol map
    
    This function will only execute once

## TODO dial.go<a id="sec-2-16" name="sec-2-16"></a>

### Types<a id="sec-2-16-1" name="sec-2-16-1"></a>

1.  [type Dialer struct {](file:///usr/local/go/src/net/dial.go)

    A Dialer contains options for connecting to an address. 
    
    The zero value for each field is equivalent to dialing without that
    option. 
    
    [func (d \*Dialer) deadline(ctx context.Context, now time.Time) (earliest time.Time) {](file:///usr/local/go/src/net/dial.go)
    Returns the earliest of now+Timeout, d.Deadline and the context's deadline

### Functions<a id="sec-2-16-2" name="sec-2-16-2"></a>

1.  [func partialDeadline(now, deadline time.Time, addrsRemaining int) (time.Time, error) {](file:///usr/local/go/src/net/dial.go)

    Returns the deadline to use for a single address

2.  [func parseNetwork(ctx context.Context, network string, needsProto bool) (afnet string, proto int, err error) {](file:///usr/local/go/src/net/dial.go)

    Returns afnet(ip, ip4, ip6), proto(http, https .etc) well known port no.

# internal<a id="sec-3" name="sec-3"></a>

## poll<a id="sec-3-1" name="sec-3-1"></a>

Package `poll` supports non-blocking I/O on file descriptors with polling. This
supports I/O operations that block only a goroutine, not a thread. 

Package `poll` uses a poller built into the runtime, with support from the
runtime scheduler.

### fd.go<a id="sec-3-1-1" name="sec-3-1-1"></a>

1.  Types

    1.  [type TimeoutError struct{}](file:///usr/local/go/src/internal/poll/fd.go)
    
        A simple struct which implements `error` interface and `net.Error` interface
        
        1.  [func (e \*TimeoutError) Error() string { return "i/o timeout" }](file:///usr/local/go/src/internal/poll/fd.go)
        
        2.  [func (e \*TimeoutError) Timeout() bool { return true }](file:///usr/local/go/src/internal/poll/fd.go)
        
        3.  [func (e \*TimeoutError) Temporary() bool { return true }](file:///usr/local/go/src/internal/poll/fd.go)

2.  Variables

    Definitions for: 
    
    1.  [ErrNetClosing](file:///usr/local/go/src/internal/poll/fd.go)
    
    2.  [ErrFileClosing](file:///usr/local/go/src/internal/poll/fd.go)
    
    3.  [ErrNoDeadline](file:///usr/local/go/src/internal/poll/fd.go)
    
        ErrNoDeadline is returned when a request is made to set a deadline on a
        file type that does not use the poller
    
    4.  [ErrTimeout](file:///usr/local/go/src/internal/poll/fd.go)

3.  Functions

    1.  [func consume(v \*{}{}byte, n int64)](file:///usr/local/go/src/internal/poll/fd.go)
    
        Removes data from a slice of byte slices, for writev

### fd\_poll\_runtime.go<a id="sec-3-1-2" name="sec-3-1-2"></a>

1.  Types

    1.  [type pollDesc struct {](file:///usr/local/go/src/internal/poll/fd_poll_runtime.go)
    
            type pollDesc struct {
                runtimeCtx uintptr
            }
        
        1.  [func (pd \*pollDesc) init(fd \*FD) error {](file:///usr/local/go/src/internal/poll/fd_poll_runtime.go)
        
            Init poll in runtime for `fd.Sysfd`
            
            1.  Init poll server once in runtime
            2.  Open poll in runtime for `fd.Sysfd` via `runtime_pollOpen` and save
                ctx returned to `pd.runtimeCtx`
        
        2.  [func (pd \*pollDesc) close() {](file:///usr/local/go/src/internal/poll/fd_poll_runtime.go)
        
            Stop polling for `pd.runtimeCtx`, hence the corresponding fd in
            `fd.Sysfd` 
        
        3.  [func (pd \*pollDesc) evict() {](file:///usr/local/go/src/internal/poll/fd_poll_runtime.go)
        
            Evicts fd from the pending list, unblocking any I/O running on fd. 
        
        4.  [func (pd \*pollDesc) prepare(mode int, isFile bool) error {](file:///usr/local/go/src/internal/poll/fd_poll_runtime.go)
        
            Set poll mode via `runtime_pollReset`, mode can be 'r' or 'w'
        
        5.  [func (pd \*pollDesc) prepareWrite(isFile bool) error {](file:///usr/local/go/src/internal/poll/fd_poll_runtime.go)
        
        6.  [func (pd \*pollDesc) prepareRead(isFile bool) error {](file:///usr/local/go/src/internal/poll/fd_poll_runtime.go)
        
        7.  [func (pd \*pollDesc) wait(mode int, isFile bool) error {](file:///usr/local/go/src/internal/poll/fd_poll_runtime.go)
        
            Wrap `runtime_pollWait` to actually wait for readable or writable 
        
        8.  [func (pd \*pollDesc) waitRead(isFile bool) error {](file:///usr/local/go/src/internal/poll/fd_poll_runtime.go)
        
        9.  [func (pd \*pollDesc) waitWrite(isFile bool) error {](file:///usr/local/go/src/internal/poll/fd_poll_runtime.go)
        
        10. [func (pd \*pollDesc) waitCanceled(mode int) {](file:///usr/local/go/src/internal/poll/fd_poll_runtime.go)
        
            FIXME: Wrap `runtime_pollWaitCanceled` to cancel wait???
        
        11. [func (pd \*pollDesc) pollable() bool {](file:///usr/local/go/src/internal/poll/fd_poll_runtime.go)
        
            Return true if `pd.runtimeCtx` is not zero, i.e., not closed
        
        12. [func setDeadlineImpl(fd \*FD, t time.Time, mode int) error {](file:///usr/local/go/src/internal/poll/fd_poll_runtime.go)
        
            Set poll timeout, with some error handling for time overflow. 
        
        13. [func (fd \*FD) SetDeadline(t time.Time) error {](file:///usr/local/go/src/internal/poll/fd_poll_runtime.go)
        
        14. [func (fd \*FD) SetReadDeadline(t time.Time) error {](file:///usr/local/go/src/internal/poll/fd_poll_runtime.go)
        
        15. [func (fd \*FD) SetWriteDeadline(t time.Time) error {](file:///usr/local/go/src/internal/poll/fd_poll_runtime.go)
        
            Call setDeadlineImpl to set different timeout

2.  Functions

    1.  [func PollDescriptor() uintptr {](file:///usr/local/go/src/internal/poll/fd_poll_runtime.go)
    
        Wraps `runtime_pollServerDescriptor` to return the descriptor being used
        by the poller. 
        
        FIXME: Why this function does not require `runtimeCtx` ???

### fd\_mutex.go<a id="sec-3-1-3" name="sec-3-1-3"></a>

1.  Types

    1.  [type fdMutex struct {](file:///usr/local/go/src/internal/poll/fd_mutex.go)
    
            type fdMutex struct {
                state uint64
                rsema uint32
                wsema uint32
            }
        
        `fdMutex.state` is organized as (numbers in [ ] is bit indices, starting
        from 0):
        
        20 bits [63-44]: number of outstanding write waiters
        20 bits [43-24]: number of outstanding read waiters
        20 bits [23-4]: total number of references (read+write+misc)
        1 bit [ 3 ]: lock for misc operations 
        1 bit [ 2 ]: lock for write operations
        1 bit [ 1 ]: lock for read operations 
        1 bit [ 0 ]: whether FD is closed, if set all subsequent lock operations
        will fail
        
        1.  [func (mu \*fdMutex) incref() bool {](file:///usr/local/go/src/internal/poll/fd_mutex.go)
        
            Reports whether mu is available for reading or writing
            
            1.  read old value **atomically**
            2.  then mutexRef (which is 0x8, i.e., 1 << 3) to get new value.
            3.  **Atomically** compare the value at `mu.state` with old value
                -   if the same, **atomically** swapped new value with that stored at
                    `mu.state` and return true, i.e., **we've successfully incremented
                    the references**,
                -   otherwise, i.e., not the same, some other goroutine has increased
                    the references, go over step 1) to 3) again until we managed to
                    increase the references
        
        2.  [func (mu \*fdMutex) increfAndClose() bool {](file:///usr/local/go/src/internal/poll/fd_mutex.go)
        
            Sets the state of mu to closed. Returns false if the file was already
            closed. 
            
            Similar steps with `incref`, with additional steps to release read and
            write semaphores. 
        
        3.  [func (mu \*fdMutex) decref() bool {](file:///usr/local/go/src/internal/poll/fd_mutex.go)
        
            Reverse operation of `incref`, similar logic except the way to calculate
            new value
            
            Reports whether there is no remaining reference
        
        4.  [func (mu \*fdMutex) rwlock(read bool) bool {](file:///usr/local/go/src/internal/poll/fd_mutex.go)
        
            Adds a reference to mu and locks mu. 
            
            **Reports whether mu is available for reading or writing**
            
            Detailed logic is:
            1.  read old value in `mu.state` **atomically**
            2.  If mutex is already closed, return false directly
            3.  Check if mutexBit in old value is set(different bit for read and
                write)
                -   If not, set mutexBit and add a mutexRef to get new value
                -   Else, add corresponding mutexWait to old value to get new value,
                    meaning that one is waiting
            4.  Lastly, **atomically** check old value and that stored in `mu.state`
                -   If the same, atomically swap old value with new value.
                    -   If mutexBit in old value is not set, i.e., mutex not locked 
                        return true, indicating that lock acquired successfully
                    
                    -   Otherwise, lock is held by others, call `runtime_Semacquire` to
                        try to acquire the semaphore. (if semaphore is less than 0, the
                        calling thread will block)
                
                -   Otherwise, repeat step 1) to step 4) until either the lock is
                    closed, or we managed to lock it
        
        5.  [func (mu \*fdMutex) rwunlock(read bool) bool {](file:///usr/local/go/src/internal/poll/fd_mutex.go)
        
            Removes a reference from mu and unlocks mu
            
            **Reports whether there is no remaining reference**

### fd\_unix.go<a id="sec-3-1-4" name="sec-3-1-4"></a>

1.  Types

    1.  [type FD struct {](file:///usr/local/go/src/internal/poll/fd_unix.go)
    
        A file descriptor that can represent a network conneciton or OS file. 
        
            type FD struct {
                // Lock sysfd and serialize access to Read and Write methods.
                fdmu fdMutex
            
                // System file descriptor. Immutable until Close.
                Sysfd int
            
                // I/O poller.
                pd pollDesc
            
                // Writev cache.
                iovecs *[]syscall.Iovec
            
                // Semaphore signaled when file is closed.
                csema uint32
            
                // Whether this is a streaming descriptor, as opposed to a
                // packet-based descriptor like a UDP socket. Immutable.
                IsStream bool
            
                // Whether a zero byte read indicates EOF. This is false for a
                // message based socket connection.
                ZeroReadIsEOF bool
            
                // Whether this is a file rather than a network socket.
                isFile bool
            
                // Whether this file has been set to blocking mode.
                isBlocking bool
            }
        
        1.  [func (fd \*FD) Init(net string, pollable bool) error {](file:///usr/local/go/src/internal/poll/fd_unix.go)
        
            Initialize the FD. 
            
            This can be called multiple times on a single FD
        
        2.  [func (fd \*FD) destroy() error {](file:///usr/local/go/src/internal/poll/fd_unix.go)
        
            Closes the FD. Called when there're no remaining references. 
            
            Note that poller will be firstly closed, then followed by the closing of
            the actual fd. 
            
            Lastly, the semaphore `fd.csema` will be released
        
        3.  [func (fd \*FD) Close() error {](file:///usr/local/go/src/internal/poll/fd_unix.go)
        
            Closes the FD. The underlying file descriptor is closed by the `destroy`
            method when there're no remaining references. 
            
            1.  Firstly, close mutex and signal all semaphores blocked at the file
            2.  Unblock any I/O via `fd.pd.evict()`
            3.  Decrese reference to this FD (as it's increamented in step 1)
            4.  Lastly, blocking wait until the FD is finally closed (whether in the
                `fd.decref` in this method, or in other unlock methods).
        
        4.  [func (fd \*FD) Shutdown(how int) error {](file:///usr/local/go/src/internal/poll/fd_unix.go)
        
            Call `syscall.Shutdown` to actually shutdown the FD within protection of
            ref counters
        
        5.  [func (fd \*FD) SetBlocking() error {](file:///usr/local/go/src/internal/poll/fd_unix.go)
        
            Making the underlying FD blocking, within protection of ref counters
            
            **Misc ref/locking related methods defined in fd\_mutex.go**
        
        6.  [func (fd \*FD) incref() error {](file:///usr/local/go/src/internal/poll/fd_mutex.go)
        
        7.  [func (fd \*FD) decref() error {](file:///usr/local/go/src/internal/poll/fd_mutex.go)
        
            If the reference becomes 0, close all related resources via `fd.destroy`
        
        8.  [func (fd \*FD) readLock() error {](file:///usr/local/go/src/internal/poll/fd_mutex.go)
        
        9.  [func (fd \*FD) readUnlock() {](file:///usr/local/go/src/internal/poll/fd_mutex.go)
        
            Similar with `decref`, if there're no any other references to FD, close
            all related resources. 
        
        10. [func (fd \*FD) writeLock() error {](file:///usr/local/go/src/internal/poll/fd_mutex.go)
        
        11. [func (fd \*FD) writeUnlock() {](file:///usr/local/go/src/internal/poll/fd_mutex.go)
        
            Same as `readUnlock`
            
            **IO Related Methods**
        
        12. [func (fd \*FD) Read(p {}byte) (int, error)](file:///usr/local/go/src/internal/poll/fd_unix.go)
        
            Implements io.Reader interface
            
            1.  Acquire read lock
            2.  Call prepareRead to reset polling of fd
            3.  Then, try to read something via `syscall.Read` and save to `p`
            4.  On EAGAIN error and nonblocking case, call `fd.pd.waitRead` to wait
                for fd becoming readable
        
        13. [func (fd \*FD) Pread(p {}byte, off int64) (int, error)](file:///usr/local/go/src/internal/poll/fd_unix.go)
        
            Wraps the pread system call which read bytes starting with offset 
            
            Note that this method does not need readLock, as it specifies the offset
            it is independent from other reads
        
        14. [func (fd \*FD) ReadFrom(p {}byte) (int, syscall.Sockaddr, error) ](file:///usr/local/go/src/internal/poll/fd_unix.go)
        
            Very similar with `*FD.Read` method, with minor difference in the
            underlying syscall, i.e., changed from `syscall.Read` to `syscall.Recvfrom`
        
        15. [func (fd \*FD) ReadMsg(p {}byte, oob {}byte) (int, int, int, syscall.Sockaddr, error)](file:///usr/local/go/src/internal/poll/fd_unix.go)
        
            Similar to `*FD.ReadFrom` method, change `syscall.Recvfrom` to `syscall.Recvmsg`
        
        16. [func (fd \*FD) Write(p {}byte) (int, error)](file:///usr/local/go/src/internal/poll/fd_unix.go)
        
        17. [func (fd \*FD) Pwrite(p {}byte, off int64) (int, error)](file:///usr/local/go/src/internal/poll/fd_unix.go)
        
        18. [func (fd \*FD) WriteTo(p {}byte, sa syscall.Sockaddr) (int, error)](file:///usr/local/go/src/internal/poll/fd_unix.go)
        
        19. [func (fd \*FD) WriteMsg(p {}byte, oob {}byte, sa syscall.Sockaddr) (int, int, error)](file:///usr/local/go/src/internal/poll/fd_unix.go)
        
            All methods above are similar to their corresponding read part
        
        20. [func (fd \*FD) Accept() (int, syscall.Sockaddr, string, error) {](file:///usr/local/go/src/internal/poll/fd_unix.go)
        
            Similar to `*FD.Read` method, but wraps `accept` function, which marks
            the returned file descriptor as nonblocking and close-on-exec
            
            As Accept is kind of **read** method, we're using `fd.readLock` in this
            method. 
            
            [func accept(s int) (int, syscall.Sockaddr, string, error) {](file:///usr/local/go/src/internal/poll/sys_cloexec.go)
        
        21. [func (fd \*FD) Seek(offset int64, whence int) (int64, error) {](file:///usr/local/go/src/internal/poll/fd_unix.go)
        
            Simple wraps of syscall.Seek, within protection of ref count
        
        22. [func (fd \*FD) ReadDirent(buf {}byte) (int, error)](file:///usr/local/go/src/internal/poll/fd_unix.go)
        
            Wraps `syscall.ReadDirent`
            
            Note that this is treated like an ordinary system call, rather than a
            call that tries to fill the buffer
        
        23. [func (fd \*FD) Fchdir() error {](file:///usr/local/go/src/internal/poll/fd_unix.go)
        
        24. [func (fd \*FD) Fstat(s \*syscall.Stat\_t) error {](file:///usr/local/go/src/internal/poll/fd_unix.go)
        
            Functions below invokes the user defined function f for
            control/read/write operation 
        
        25. [func (fd \*FD) RawControl(f func(uintptr)) error {](file:///usr/local/go/src/internal/poll/fd_unix.go)
        
        26. [func (fd \*FD) RawRead(f func(uintptr) bool) error {](file:///usr/local/go/src/internal/poll/fd_unix.go)
        
        27. [func (fd \*FD) RawWrite(f func(uintptr) bool) error {](file:///usr/local/go/src/internal/poll/fd_unix.go)