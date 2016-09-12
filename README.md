
#import <UIKit/UIKit.h>

@interface youtube : UIViewController
@property (weak, nonatomic) IBOutlet UIWebView *youtube;


@property (strong,nonatomic) NSString *Str;
@end

#import "youtube.h"

@interface youtube ()<UIWebViewDelegate>

@end

@implementation youtube

- (id)initWithNibName:(NSString *)nibNameOrNil bundle:(NSBundle *)nibBundleOrNil
{
    self = [super initWithNibName:nibNameOrNil bundle:nibBundleOrNil];
    if (self) {
        // Custom initialization
    }
    return self;
}

- (void)viewDidLoad
{
    [super viewDidLoad];
    // Do any additional setup after loading the view from its nib.
    NSString *VideoUrl=[NSString stringWithFormat:@"http://janamtv.com/streaminfo/janam_str.php",_Str];
    {
    NSString *VideoHtml=[NSString stringWithFormat:@"\
                         <html>\
                         <head>\
                         <style type=\"text/css\">\
                         iframe {position:absolute; top:0%%; margin-top:0%%;}\
                         body {background-color:#000; margin:0;}\
                         </style>\
                         </head>\
                         <body>\
                         <iframe width=\"100%%\" height=\"100%%\" src=\"%@\" frameborder=\"0\" allowfullscreen></iframe>\
                         </body>\
                         </html>",VideoUrl];
        [self.youtube loadHTMLString:VideoHtml baseURL:nil];

    
}

}

- (void)didReceiveMemoryWarning
{
    [super didReceiveMemoryWarning];
    // Dispose of any resources that can be recreated.
}

@end
