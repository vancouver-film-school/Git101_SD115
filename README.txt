#Git repository for SD115 practice

hiii kyubin
Player needs RigiBody 2D

Put Colliders on everything depending on the shape 

Create 2 scripts - 1 PLayer Movement 2 Follow player
(Dont forget to assign the scripts to the things

We start under the MonoBehaviour 

private RigiBody2D _rb;


Under the void Start 

_rb = GetComponent<RigiBody2D>();



at the end we start the void Movement()
{

}









 public float walkSpeed = 5f;
 public float runSpeed = 10f;
 public float jumpForce = 10f;

 private Rigidbody2D _rb;
 private bool _isRunning = false;

 public int nJump = 0;

 private bool _isGrounded = false;
 private Collider2D _playerCollider;
 private Animator _animator;
 private SpriteRenderer _spriteRender; 




  if (Input.GetButtonDown("Jump")) //&& (nJump < 69)
  {
      if (_isGrounded)

      {
          _rb.linearVelocity = new Vector2(_rb.linearVelocity.x, jumpForce);
          nJump++;
          //_animator.SetBool("isJumping", true);





































    private Rigidbody2D _rb;
    public float walkSpeed = 5f;
    public float runSpeed = 10f;
    private float jumpForce = 10f;
    public int nJumps = 0;
    private bool _isRunning = false;

    // Start is called once before the first execution of Update after the MonoBehaviour is created
    void Start()
    {
        _rb = GetComponent<Rigidbody2D>();
    }

    // Update is called once per frame
    void Update()
    {
        Movement();
        Jumping();
    }

    void Movement()
    {
        float moveInput = Input.GetAxis("Horizontal");
        if (Input.GetKey(KeyCode.LeftShift))
        {
            _isRunning = true;
        }
        else
        {
            _isRunning = false;
        }

        float speed = _isRunning ? runSpeed : walkSpeed;

       _rb.linearVelocity = new Vector2(moveInput * speed, _rb.linearVelocity.y); 
    }

    void Jumping()
    {
        if (Input.GetButtonDown("Jump")) //&& nJumps <4)
        {
            _rb.linearVelocity = new Vector2(_rb.linearVelocity.x, jumpForce);
            nJumps ++ 1;
        }
       
    }

















Follow Player


    public float followSpeed = 5f;
    public Transform player ;
   
    // Start is called once before the first execution of Update after the MonoBehaviour is created
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
       transform.position = Vector2.MoveTowards(transform.position, player.position, Time.deltaTime *followSpeed); 
    }
}


